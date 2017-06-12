# BridgePoint Model Translation Exercises

This document contains exercises to teach the user about the BridgePoint Generator and 
how it is used in the model translation process for xtUML models.  

## Chapter 1. Getting Started

This chapter describes the purpose and use of this document, lists other related documents, and presents the conventions used within.

### 1. Purpose and Intended Audience

This section explains the intent of this document and describes its usage.

#### 1.1. Purpose of the Exercises

The purpose of this guide is to teach the user of BridgePoint Generator to understand how archetype files 
interact with the Generator and are used to produce target code from a xtUML model. Essential tasks that 
this guide will enable the user to perform include the following.  
 
* Create an archetype.
* Process an archetype using BridgePoint.
* Understand the model compiler meta-model.

#### 1.2. Intended Audience

This guide is written for software engineers who are using the BridgePoint environment to create and use 
xtUML models and the MC-3020 model compiler. It assumes that the user is familiar with the ANSI C programming 
language and general usage of the development platform and its software development utilities.  

#### 1.3. Additional Resources

The following additional documentation will be helpful to the reader:

* Object Action Language Manual (bpalref.pdf )
* BridgePoint Help > Help Contents > BridgePoint UML Suite Help

#### 1.4. Running Your Archetype

BridgePoint performs all of the code generation underneath the gen folder in your project. In these exercises, 
you will create a number of archetype files. We suggest creating a new archetype for each exercise named 
ex1.arc, ex2.arc, etc... These should be saved into the folder my arcs (or whatever you want to call it when 
you create it) in your project. Then copy the desired archetype to your gen folder when you want to run it.   

When you select Build Project for your project, BridgePoint will look for an archetype (*.arc) file in the 
gen folder, if it finds one, it will load the model into the "gen database", run the archetype, and then exit 
without finishing the rest of the model compilation process.   

Before proceeding, you will need to create a new xtUML project in BridgePoint and load a model with some data into the project. Request a sample model from your instructor if you do not already have one.

## Chapter 2. Exercises

This chapter presents the exercises, starting with the simplest and progressing from there.

### 1. Exercise 1

Here we go! Get ready, get set, generate.

#### 1.1. What we want to accomplish

The purpose of this exercise is to:

* Learn how to run an archetype in BridgePoint.
* Learn about selection and iteration.
* Understand where data is kept in the gen database.

#### 1.2. Task

Create a report on the screen (using .print) that shows the names of all the classes in any model.

#### 1.3. Things to consider...

* Create file ex1.arc.
* What gen database table contains these names?
* The design guide section 5.1 contains useful information.

### 2. Exercise 2

Wow, that was cool! Now, teach me the next step.

#### 2.1. What we want to accomplish

The purpose of this exercise is to:

* Learn how to create a file using an archetype.

#### 2.2. Task

Write the same report as in Exercise 1 to a disk file called ex2.txt.

### 3. Exercise 3

Look, Ma! I can generate code.

#### 3.1. What we want to accomplish

The purpose of this exercise is to:

* Take what you learned in Exercise 2 and generate "real" code.

#### 3.2. Task

Create an archetype to define a C struct definition for the classes in any model. The struct should contain member data for each attribute, but you may assume that all attributes are of type 'int'. Output your results to ex3.c.

##### 3.3. Things to consider...

* You know where class names are stored in the gen database. Where are attribute names stored?

* How are the class names and attribute names associated in the gen database?

### 4. Exercise 4

So we've gathered some bricks. Let's start building a wall.

#### 4.1. What we want to accomplish

The purpose of this exercise is to:

* Take the building blocks and keep going up.

#### 4.2. Task

Modify the output of Exercise 3 so that it outputs each struct definition to a separate file called <classname>.h .

#### 4.3. Things to consider...

* What is a substitution variable? Where can it be used?

### 5. Exercise 5

Up, up, up, we go.

#### 5.1. What we want to accomplish

The purpose of this exercise is to:

* Learn where datatypes are stored in the gen database.
* Learn how to associate and use datatypes.

#### 5.2. Task

Modify the output of Exercise 4 so that the member data is declared using the data type name found across R114.

### 6. Exercise 6

Man, get real! Uh...I mean float.

#### 6.1. What we want to accomplish

The purpose of this exercise is to:

* Learn how to call archetype subroutines.
* Learn how to change model datatypes into C datatypes.

#### 6.2. Task

Modify the output of Exercise 5 so that the data members are declared using C compatible data types. You will need to create an archetype function to convert the datatype names in the model into the equivalent C type.

### 7. Exercise 7 and Beyond

Here are some advanced exercises the reader may wish to attempt to solve for additional practice. They are oriented to Java-based code.

#### 7.1. Exercise 7

Build an enumeration of constants, one for each State. Have your archetypes generate a private integer currentState variable for each each class that needs one. You should also extend your current archetype to suppress the modeled current_state attribute if you have not done so already. Select an appropriate initial value for currentState and generate code to set it.

#### 7.2. Exercise 8

Generate an inner class declaration for each event accepted by a class's state machine. An instance of this inner class shall contain data members for each event data item carried by the event.

#### 7.3. Exercise 9

Again, for each event, create a public method of the class that accepts the incoming event and its data items, constructs the correct instance of the inner classes created in Exercise 7, populates the data members with the values supplied as arguments to the call and enqueues the event in a suitable event queue container.

#### 7.4. Exercise 10

Create a method called procEvent that takes the next event from the event queue created in Exercise 8 and returns true if an event was processed, false if the queue was empty or the event was ignored. Make the method check the currentState.

Hint: there are many ways to do this but a straightforward approach that works well in Java is to generate a nested switch. This is the approach used by MC-Java, our own internal Java model compiler. Another way is to build a two dimensional array of Function instances. This can be initialized with handler functions for Can't Happen, Ignored and functions called enter<StateName> for each state. Choose another way to do it if you like. Don't attempt to generate code for the state actions at this time.

## Chapter 3. Exercise Answers
This chapter presents the the answers to the exercises.

### 1. Exercise 1 Answer
```
.//
.// ex1.arc
.//
.//
Beginning of List of Object Names
.select many obj_set from instances of O_OBJ
.for each obj_inst in obj_set
  .print "Object name is ${obj_inst.Name}\n"
.end for
End of List of Object Names
```

### 2. Exercise 2 Answer
```
.//
.// ex2.arc
.//
.//
Beginning of List of Object Names
.select many obj_set from instances of O_OBJ
.for each obj_inst in obj_set
  Object name is ${obj_inst.Name}
.end for
End of List of Object Names
.//
.emit to file "ex2.txt"
```

### 3. Exercise 3 Answer
```
.//
.// ex3.arc
.//
.//
.select many obj_set from instances of O_OBJ
.for each obj_inst in obj_set
struct ${obj_inst.Name} {
  .select many attr_set related by obj_inst->O_ATTR[R102]
  .for each attr_inst in attr_set
  int ${attr_inst.Name};
  .end for
};
.end for
.//
.emit to file "ex3.c"
```

### 4. Exercise 4 Answer
```
.//
.// ex4.arc
.//
.//
.select many obj_set from instances of O_OBJ
.for each obj_inst in obj_set
struct ${obj_inst.Name} {
.select many attr_set related by obj_inst->O_ATTR[R102]
.for each attr_inst in attr_set
  int ${attr_inst.Name};
.end for
};
.//
.emit to file "${obj_inst.Name}.h"
.end for
```

### 5. Exercise 5 Answer
```
.//
.// ex5.arc
.//
.//
.select many obj_set from instances of O_OBJ
.for each obj_inst in obj_set
struct ${obj_inst.Name} {
.select many attr_set related by obj_inst->O_ATTR[R102]
.for each attr_inst in attr_set
  ${attr_inst->S_DT[R114].Name} ${attr_inst.Name};
.end for
};
.//
.emit to file "${obj_inst.Name}.h"
.end for
```

### 6. Exercise 6 Answer
```
.//
.// ex6.arc
.//
.//
.// This function retrieves a C type given  model type
.function lookupCType
.param integer coreType
  .assign attr_cType = ""
  .// The MC3020 model defines the 
  .// following as values for "Core Data Types"
  .//
  .if ( coreType == 0 )
    .// 0 = void
    .assign attr_cType = "void"
  .elif ( coreType == 1 )
    .// 1 = boolean
    .assign attr_cType = "char"
  .elif ( coreType == 2 )
    .// 2 = integer
    .assign attr_cType = "int"
  .elif ( coreType == 3 )
    .// 3 = real
    .assign attr_cType = "float"
  .elif ( coreType == 4 )
    .// 4 = string
    .// WARNING! 100 is an arbitrary value
    .assign attr_cType = "char[100]"
  .elif ( coreType == 5 )
    .// 5 = integer
    .assign attr_cType = "int"
  .elif ( coreType == 6 )
    .// 6 = current_state
    .assign attr_cType = "void*"
  .elif ( coreType == 7 )
    .// 7 = same_as_base
    .assign attr_cType = "void*"
  .elif ( coreType == 8 )
    .// 8 = inst_ref<Object>
    .assign attr_cType = "void*"
  .elif ( coreType == 9 )
    .// 9 = inst_ref_set<Object>
    .assign attr_cType = "void*"
  .elif ( coreType == 10 )
    .// 10= inst<Event>
    .assign attr_cType = "void*"
  .elif ( coreType == 11 )
    .// 11= inst<Mapping>
    .assign attr_cType = "void*
  .elif ( coreType == 12 )
    .// 12= inst_ref<Mapping>
    .assign attr_cType = "void*"
  .else
    .assign attr_cType = "Error Unexpected Type (${coreType})"
  .end if
.end function
.//
.// This function retrieves a C type given  model type
.function getCType
.param inst_ref dt_inst
  .assign attr_modelType = dt_inst.Name
  .assign attr_Core_Type = -1
  .assign attr_cType = ""
  .assign attr_enumData = ""
  .//
  .select one cdt related by dt_inst->S_CDT[R17]
  .select one udt related by dt_inst->S_UDT[R17]
  .select one edt related by dt_inst->S_EDT[R17]
  .//
  .if ( not_empty cdt )
    .assign attr_Core_Type = cdt.Core_Typ
    .// Call a function to get the C type from this integer value
    .invoke lookupResult = lookupCType(attr_Core_Type)
    .assign attr_cType = lookupResult.cType
  .elif ( not_empty udt )
    .// Each user data-type maps to a core data type
    .select one udt_cdt related by udt->S_CDT[R18]
    .assign attr_Core_type = udt_cdt.CoreTyp
    .// Call a function to get the C type from this integer value
    .invoke lookupResult = lookupCType(attr_Core_Type)
    .assign attr_cType = lookupResult.cType
  .elif ( not_empty edt )
    .// I'm taking the easy way out and assuming that the
    .// enum definition is made else where and so we can
    .// go ahead and declare this here.
    .// 
    .assign attr_cType = dt_inst.Name
  .else
    .assign attr_cType = "Error! (${attr_cType})"
  .end if
.end function
.//
.select many class_set from instances of O_OBJ
.for each class_inst in class_set
.// class comment followed by class name
/* class comment */
struct ${class_inst.Name} {
  .// Now iterate over attributes
  .select many a_set related by class_inst->O_ATTR[R102]
  .for each a_inst in a_set
    .select one dt_inst related by a_inst->S_DT[R114]
    .// Call a function to get the C data type
    .invoke myResult = getCType(dt_inst)
    .// This is a class attribute (always integer)
  ${myResult.cType} ${a_inst.Name}; /* comment */
  .end for 
  .// Below is the closing curly for the generated struct 
};
.emit to file "${class_inst.Name}.c"
.end for
```  

### 7. Exercise 7 Answer
```
.//
.// ex7.arc
.//
.//
.function appendStateData
	.param inst_ref object
	.//
	.// if the given class has a state model
	.select one stateModel related by object->SM_ISM[R518]->SM_SM[R517]
	.if (not_empty stateModel) 
		.// for each state in the state model
		.select any initialState related by stateModel->SM_STATE[R501]
		.select many states related by stateModel->SM_STATE[R501]
		.for each state in states
			.// add a constant for this state's ID
	private static final int stateID_$o{state.Name} = ${state.Numb};
			.//	
			.// if this state's number is the lowest so far
			.if (state.Numb < initialState.Numb)
				.// remember this state as the one currently most likely to be the initial
				.assign initialState = state
			.end if
		.end for
		.//
		.// add an attribute for which state an instance is currently in
	private int currentState = stateID_$o{initialState.Name};
	.end if 
.end function
.//
.function getImplementationTypeName
	.param string modelName
	.assign attr_name = ""
	.if (modelName == "boolean") 
		.assign attr_name = modelName
	.elif (modelName == "unique_id") 
		.assign attr_name = "long"
	.elif (modelName == "inst_ref<Mapping>") 
		.assign attr_name = "Mapping"
	.elif (modelName == "inst<Event>") 
		.assign attr_name = "Event"
	.elif ((modelName == "integer") or (modelName == "state<State_Model>")) 
		.assign attr_name = "int"
	.end if
.end function
.//
.//
.// for each object class in the models
.select many objects from instances of O_OBJ
.for each object in objects
	.// output the opening of this class's declaration
	.assign name = "$cr{object.Name}"
class ${name} 
{
	.select many attributes related by object->O_ATTR[R102]
	.for each attribute in attributes
		.// if this isn't one of the attributes which we are to suppress
		.if (attribute.Name != "current_state")
			.// if this attribute is a referential attribute
			.select one referential related by attribute->O_RATTR[R106]
			.if (not_empty referential)
				.// use the name of the corresponding base attribute, instead
				.select one attribute related by referential->O_BATTR[R113]->O_ATTR[R106]
			.end if
			.//
			.// if this attribute's data-type is a user-type
			.select one type related by attribute->S_DT[R114]
			.select one userType related by type->S_UDT[R17]
			.if (not_empty userType)
				.// resolve the user-type's core-type, and use that instead
				.select one type related by userType->S_CDT[R18]->S_DT[R17]
			.end if
			.//
			.// if this attribute's data-type is an enumeration
			.select one enumeration related by type->S_EDT[R17]
			.assign typeName = type.Name
			.if (not_empty enumeration)
				.// treat this enumeration as a simple integer variable
				.assign typeName = "integer"
			.end if
			.//
			.// map the type's name to the name of its corresponding 
			.// implementation language element
			.invoke result = getImplementationTypeName(typeName)
			.assign typeName = result.name
			.//
			.// output the attribute declaration
	${typeName} $o{attribute.Name};
		.end if
	.end for
	.//
	.// append the state fields
	
	.invoke stateData = appendStateData(object)
${stateData.body}	
	.//
	.// output the closing of this class's declaration
}
	.//
	.// save the generated text to a file of this class's name
	.emit to file "${name}.java"
.end for
```  

### 8. Exercise 8 Answer
```
.//
.// ex8.arc
.//
.//
.function appendEventClasses
	.param inst_ref object
	.//
	.// if the given class has a state model
	.select one stateModel related by object->SM_ISM[R518]->SM_SM[R517]
	.if (not_empty stateModel) 
		.select many events related by stateModel->SM_STATE[R501]->SM_SEME[R503]->SM_SEVT[R503]->SM_EVT[R525]
		.for each event in events
			.assign temp = "$o{event.Mning}"
		
	private static class ${temp}Event
	{
			.// for each data member of this event
			.select many dataMembers related by event->SM_SUPDT[R520]->SM_SDI[R522]->SM_EVTDI[R522]
			.for each dataMember in dataMembers
				.// output a declaration for this data member
				.select one type related by dataMember->S_DT[R524]
				.invoke result = getImplementationTypeName(type.Name)
		public ${result.name} ${dataMember.Name};
			.end for
	}
		.end for
	.end if
.end function
.//
.function appendStateData
	.param inst_ref object
	.//
	.// if the given class has a state model
	.select one stateModel related by object->SM_ISM[R518]->SM_SM[R517]
	.if (not_empty stateModel) 
		.// for each state in the state model
		.select any initialState related by stateModel->SM_STATE[R501]
		.select many states related by stateModel->SM_STATE[R501]
		.for each state in states
			.// add a constant for this state's ID
	private static final int stateID_$o{state.Name} = ${state.Numb};
			.//	
			.// if this state's number is the lowest so far
			.if (state.Numb < initialState.Numb)
				.// remember this state as the one currently most likely to be the initial
				.assign initialState = state
			.end if
		.end for
		.//
		.// add an attribute for which state an instance is currently in
	private int currentState = stateID_$o{initialState.Name};
	.end if 
.end function
.//
.function getImplementationTypeName
	.param string modelName
	.assign attr_name = ""
	.if (modelName == "boolean") 
		.assign attr_name = modelName
	.elif (modelName == "unique_id") 
		.assign attr_name = "long"
	.elif (modelName == "inst_ref<Mapping>") 
		.assign attr_name = "Mapping"
	.elif (modelName == "inst<Event>") 
		.assign attr_name = "Event"
	.elif ((modelName == "integer") or (modelName == "state<State_Model>")) 
		.assign attr_name = "int"
	.end if
.end function
.//
.//
.// for each object class in the models
.select many objects from instances of O_OBJ
.for each object in objects
	.// output the opening of this class's declaration
	.assign name = "$cr{object.Name}"
class ${name} 
{
	.select many attributes related by object->O_ATTR[R102]
	.for each attribute in attributes
		.// if this isn't one of the attributes which we are to suppress
		.if (attribute.Name != "current_state")
			.// if this attribute is a referential attribute
			.select one referential related by attribute->O_RATTR[R106]
			.if (not_empty referential)
				.// use the name of the corresponding base attribute, instead
				.select one attribute related by referential->O_BATTR[R113]->O_ATTR[R106]
			.end if
			.//
			.// if this attribute's data-type is a user-type
			.select one type related by attribute->S_DT[R114]
			.select one userType related by type->S_UDT[R17]
			.if (not_empty userType)
				.// resolve the user-type's core-type, and use that instead
				.select one type related by userType->S_CDT[R18]->S_DT[R17]
			.end if
			.//
			.// if this attribute's data-type is an enumeration
			.select one enumeration related by type->S_EDT[R17]
			.assign typeName = type.Name
			.if (not_empty enumeration)
				.// treat this enumeration as a simple integer variable
				.assign typeName = "integer"
			.end if
			.//
			.// map the type's name to the name of its corresponding 
			.// implementation language element
			.invoke result = getImplementationTypeName(typeName)
			.assign typeName = result.name
			.//
			.// output the attribute declaration
	${typeName} $o{attribute.Name};
		.end if
	.end for
	.//
	.// append the state fields
	
	.invoke stateData = appendStateData(object)
${stateData.body}	
	.//
	.// append the event inner classes
	.invoke eventClasses = appendEventClasses(object)
${eventClasses.body}	
}
	.//
	.// save the generated text to a file of this class's name
	.emit to file "${name}.java"
.end for
```  

### 9. Exercise 9 Answer
```
.//
.// ex9.arc
.//
.//
.function appendEventClasses
	.param inst_ref object
	.//
	.// if the given class has a state model
	.select one stateModel related by object->SM_ISM[R518]->SM_SM[R517]
	.if (not_empty stateModel) 
		.// if the class's state model accepts events
		.select many events related by stateModel->SM_STATE[R501]->SM_SEME[R503]->SM_SEVT[R503]->SM_EVT[R525]
		.if (not_empty events) 
			.// add a queue to hold the incoming events
	private List events = new ArrayList();
		.end if 
		.//
		.// for event the state model accepts
		.for each event in events
			.// add an inner class to represent this event
			.assign eventName = "$o{event.Mning}"
		
	private static class ${eventName}Event
	{
			.// for each field of this event
			.select many fields related by event->SM_SUPDT[R520]->SM_SDI[R522]->SM_EVTDI[R522]
			.for each field in fields
				.// output a declaration for this field
				.select one type related by field->S_DT[R524]
				.invoke result = getImplementationTypeName(type.Name)
		public ${result.name} ${field.Name};
			.end for
	}
	
			.// start to add a method to the inner class that constructs an instance of this 
			.// kind of event from parameters corresponding to the fields of this event
			.assign method = "public void on_${eventName}(";
			.//
			.// for each field of this event
			.for each field in fields
				.// add a parameter to this method that contains the data to go in this
				.// field of the event
				.select one type related by field->S_DT[R524]
				.invoke result = getImplementationTypeName(type.Name)
				.if (not_first fields) 
					.assign method = method + ", "
				.end if
				.assign method = method + "${result.name} ${field.Name}"
			.end for
	${method})
	{
		${eventName}Event event = new ${eventName}Event();
			.// for each field of this event
			.for each field in fields
				.// set this field's value to that of the corresponding method parameter
				.select one type related by field->S_DT[R524]
				.invoke result = getImplementationTypeName(type.Name)
		event.${field.Name} = ${field.Name};
			.end for
		events.add(event);
	}
		.end for
	.end if
.end function
.//
.function appendStateData
	.param inst_ref object
	.//
	.// if the given class has a state model
	.select one stateModel related by object->SM_ISM[R518]->SM_SM[R517]
	.if (not_empty stateModel) 
		.// for each state in the state model
		.select any initialState related by stateModel->SM_STATE[R501]
		.select many states related by stateModel->SM_STATE[R501]
		.for each state in states
			.// add a constant for this state's ID
	private static final int stateID_$o{state.Name} = ${state.Numb};
			.//	
			.// if this state's number is the lowest so far
			.if (state.Numb < initialState.Numb)
				.// remember this state as the one currently most likely to be the initial
				.assign initialState = state
			.end if
		.end for
		.//
		.// add an attribute for which state an instance is currently in
	private int currentState = stateID_$o{initialState.Name};
	.end if 
.end function
.//
.function getImplementationTypeName
	.param string modelName
	.assign attr_name = ""
	.if (modelName == "boolean") 
		.assign attr_name = modelName
	.elif (modelName == "unique_id") 
		.assign attr_name = "long"
	.elif (modelName == "inst_ref<Mapping>") 
		.assign attr_name = "Mapping"
	.elif (modelName == "inst<Event>") 
		.assign attr_name = "Event"
	.elif ((modelName == "integer") or (modelName == "state<State_Model>")) 
		.assign attr_name = "int"
	.end if
.end function
.//
.//
.// for each object class in the models
.select many objects from instances of O_OBJ
.for each object in objects
	.// output the opening of this class's declaration
	.assign name = "$cr{object.Name}"
class ${name} 
{
	.select many attributes related by object->O_ATTR[R102]
	.for each attribute in attributes
		.// if this isn't one of the attributes which we are to suppress
		.if (attribute.Name != "current_state")
			.// if this attribute is a referential attribute
			.select one referential related by attribute->O_RATTR[R106]
			.if (not_empty referential)
				.// use the name of the corresponding base attribute, instead
				.select one attribute related by referential->O_BATTR[R113]->O_ATTR[R106]
			.end if
			.//
			.// if this attribute's data-type is a user-type
			.select one type related by attribute->S_DT[R114]
			.select one userType related by type->S_UDT[R17]
			.if (not_empty userType)
				.// resolve the user-type's core-type, and use that instead
				.select one type related by userType->S_CDT[R18]->S_DT[R17]
			.end if
			.//
			.// if this attribute's data-type is an enumeration
			.select one enumeration related by type->S_EDT[R17]
			.assign typeName = type.Name
			.if (not_empty enumeration)
				.// treat this enumeration as a simple integer variable
				.assign typeName = "integer"
			.end if
			.//
			.// map the type's name to the name of its corresponding 
			.// implementation language element
			.invoke result = getImplementationTypeName(typeName)
			.assign typeName = result.name
			.//
			.// output the attribute declaration
	private ${typeName} $o{attribute.Name};
		.end if
	.end for
	.//
	.// append the state fields
	
	.invoke stateData = appendStateData(object)
${stateData.body}	
	.//
	.// append the event inner classes
	.invoke eventClasses = appendEventClasses(object)
${eventClasses.body}	
}
	.//
	.// save the generated text to a file of this class's name
	.emit to file "${name}.java"
.end for
```  

### 10. Exercise 10 Answer
```
.//
.// ex10.arc
.//
.//
.function appendEventProcessingMethod
	.param inst_ref object
	.//
	.// if the given class has a state model
	.select one stateModel related by object->SM_ISM[R518]->SM_SM[R517]
	.if (not_empty stateModel) 
		.// declare the event processing method
	public boolean processEvent()
	{
		if (events.isEmpty()) return false;
		
		Event event = events.remove(0);
		
		.// for each state in the state model
		int nextStateID = -1;
		switch(currentStateID) {
		.select many states related by stateModel->SM_STATE[R501]
		.for each state in states
			.// add a case statement for this state's ID
			case stateID_$o{state.Name} :  
			.//
			.// for each transition out of this state
			.select many transitions related by state->SM_SEME[R503]
			.assign foundNewStateTrasition = false
			.for each transition in transitions
				.// if this transition is also a new-state-transition
				.select one newStateTransition related by transition->SM_NSTXN[R504]
				.if (not_empty newStateTransition)
					.// detm the next state from this transition
					.select one nextState related by newStateTransition->SM_TXN[R507]->SM_STATE[R506]
					.//
					.// detm the event that causes this transition
					.select one event related by transition->SM_SEVT[R503]->SM_EVT[R525]
					.//
					.// generate a test for executing this transition
					.assign test = "";
					.if (not foundNewStateTrasition)
						.assign foundNewStateTrasition = true
					.else
					 	.assign test = test + "else "
					.end if
					.assign test = test + "if (event instanceof $o{event.Mning}Event) nextStateID = stateID_$o{nextState.Name};"
				${test}
				.end if
			.end for
				break;
		.end for
		}
	.end if 
		
		if (nextStateID != -1) currentStateID = nextStateID;
		return nextStateID != -1;
	}
.end function
.//
.//
.function appendEventClasses
	.param inst_ref object
	.//
	.// if the given class has a state model
	.select one stateModel related by object->SM_ISM[R518]->SM_SM[R517]
	.if (not_empty stateModel) 
		.// if the class's state model accepts events
		.select many events related by stateModel->SM_STATE[R501]->SM_SEME[R503]->SM_SEVT[R503]->SM_EVT[R525]
		.if (not_empty events) 
			.// add a queue to hold the incoming events
	private List events = new ArrayList();
		.end if 
		.//
		.// for each event the state model accepts
		.for each event in events
			.// add an inner class to represent this event
			.assign eventName = "$o{event.Mning}"
		
	private static class ${eventName}Event extends Event
	{
			.// for each field of this event
			.select many fields related by event->SM_SUPDT[R520]->SM_SDI[R522]->SM_EVTDI[R522]
			.for each field in fields
				.// output a declaration for this field
				.select one type related by field->S_DT[R524]
				.invoke result = getImplementationTypeName(type.Name)
		public ${result.name} ${field.Name};
			.end for
	}
	
			.// start to add a method to the inner class that constructs an instance of this 
			.// kind of event from parameters corresponding to the fields of this event
			.assign method = "public void on_${eventName}(";
			.//
			.// for each field of this event
			.for each field in fields
				.// add a parameter to this method that contains the data to go in this
				.// field of the event
				.select one type related by field->S_DT[R524]
				.invoke result = getImplementationTypeName(type.Name)
				.if (not_first fields) 
					.assign method = method + ", "
				.end if
				.assign method = method + "${result.name} ${field.Name}"
			.end for
	${method})
	{
		${eventName}Event event = new ${eventName}Event();
			.// for each field of this event
			.for each field in fields
				.// set this field's value to that of the corresponding method parameter
				.select one type related by field->S_DT[R524]
				.invoke result = getImplementationTypeName(type.Name)
		event.${field.Name} = ${field.Name};
			.end for
		events.add(event);
	}
		.end for
	.end if
.end function
.//
.//
.function appendStateData
	.param inst_ref object
	.//
	.// if the given class has a state model
	.select one stateModel related by object->SM_ISM[R518]->SM_SM[R517]
	.if (not_empty stateModel) 
		.// for each state in the state model
		.select any initialState related by stateModel->SM_STATE[R501]
		.select many states related by stateModel->SM_STATE[R501]
		.for each state in states
			.// add a constant for this state's ID
	private static final int stateID_$o{state.Name} = ${state.Numb};
			.//	
			.// if this state's number is the lowest so far
			.if (state.Numb < initialState.Numb)
				.// remember this state as the one currently most likely to be the initial
				.assign initialState = state
			.end if
		.end for
		.//
		.// add an attribute for which state an instance is currently in
	private int currentStateID = stateID_$o{initialState.Name};
	.end if 
.end function
.//
.//
.function getImplementationTypeName
	.param string modelName
	.assign attr_name = ""
	.if (modelName == "boolean") 
		.assign attr_name = modelName
	.elif (modelName == "unique_id") 
		.assign attr_name = "long"
	.elif (modelName == "inst_ref<Mapping>") 
		.assign attr_name = "Mapping"
	.elif (modelName == "inst<Event>") 
		.assign attr_name = "Event"
	.elif ((modelName == "integer") or (modelName == "state<State_Model>")) 
		.assign attr_name = "int"
	.end if
.end function
.//
.//
.// for each object class in the models
.select many objects from instances of O_OBJ
.for each object in objects
	.// output the opening of this class's declaration
	.assign name = "$cr{object.Name}"
class ${name} 
{
	.select many attributes related by object->O_ATTR[R102]
	.for each attribute in attributes
		.// if this isn't one of the attributes which we are to suppress
		.if (attribute.Name != "current_state")
			.// if this attribute is a referential attribute
			.select one referential related by attribute->O_RATTR[R106]
			.if (not_empty referential)
				.// use the name of the corresponding base attribute, instead
				.select one attribute related by referential->O_BATTR[R113]->O_ATTR[R106]
			.end if
			.//
			.// if this attribute's data-type is a user-type
			.select one type related by attribute->S_DT[R114]
			.select one userType related by type->S_UDT[R17]
			.if (not_empty userType)
				.// resolve the user-type's core-type, and use that instead
				.select one type related by userType->S_CDT[R18]->S_DT[R17]
			.end if
			.//
			.// if this attribute's data-type is an enumeration
			.select one enumeration related by type->S_EDT[R17]
			.assign typeName = type.Name
			.if (not_empty enumeration)
				.// treat this enumeration as a simple integer variable
				.assign typeName = "integer"
			.end if
			.//
			.// map the type's name to the name of its corresponding 
			.// implementation language element
			.invoke result = getImplementationTypeName(typeName)
			.assign typeName = result.name
			.//
			.// output the attribute declaration
	private ${typeName} $o{attribute.Name};
		.end if
	.end for
	.//
	.// append the state fields
	
	.invoke stateData = appendStateData(object)
${stateData.body}	
	.//
	.// append the event inner classes
	.invoke eventClasses = appendEventClasses(object)
${eventClasses.body}	
	.//
	.// append the event processing method
	.invoke method = appendEventProcessingMethod(object)
${method.body}	
}
	.//
	.// save the generated text to a file of this class's name
	.emit to file "${name}.java"
.end for
```
