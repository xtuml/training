Packages group and organize the pieces of the model. They have no semantic 
meaning other than control of visibility. Since packages provide the 
organization of the various pieces of the model data, package names should 
give some indication about the data they contain.

DEMO - Draw a package couple of packages (Analysis with subpackages, Use 
Cases, Sequences, Library - Hardware, Library - HAL, System - Test, 
System - Implementation)

Packages may contain many different types of elements including sub-
packages.  They are general-purpose hierarchical organizational units of 
UML models. They can be used for storage, access control, configuration 
management, and constructing libraries containing reusable model 
fragments. To effectively employ packages, the guidelines regarding 
descriptions, naming standards, and organization, which are provided 
next, should be considered:

Descriptions:
An important guideline is to “document as you go” by entering descriptive 
information about each package you create when you create it. All too often 
analysts choose not to perform this step, surmising that they will circle 
back and add it later. This second pass to write the documentation rarely 
happens, and it is not surprising. The context and ideas that drove the 
creation of the model elements become stale or lost completely. The 
pressures of the later phases of the project outweigh a documentation pass. 
The size of the data to document often becomes so large, that the task seems 
insurmountable. Or, the original creator of the model elements has moved 
on to other work. 

Organization:
There are no hard and fast rules about where packages, either for Analysis 
or Executable modeling, should go in the hierarchy. Related packages should 
be grouped, following the rules of cohesion. That is, maximize close proximity 
of related subject matter and minimize package interdependency.

Use Separate Packages for Libraries and System Wiring:
You should create packages that serve as libraries of components. For example, 
create a package that is a library of components which models hardware 
functionality. Create another package that is a library of components that 
serve as the hardware abstraction layer (HAL). Create another package that is 
a library of components that serve as a test bench for the components elsewhere 
in the model. Create another package or packages that contain the application 
itself. Also, create packages to contain the interfaces that the various components 
expose. Then, create one or more packages that define scenarios for how the system 
is wired together using component references.  The system implementation package 
is what is passed to the model compiler for translation into implementation code.

BridgePoint allows you to wire together components themselves as well as component 
references. However, direct wiring of components is not recommended. Stick to 
creating component libraries using packages, and only wiring together component 
references in separate System Implementation packages.

DEMO - Let's consider an example using the GPS Watch case study project included 
in the BridgePoint help. Here we see a "Library" package that contains the 
components. The component interfaces are specified, but the interfaces are 
intentionally left disconnected. The wiring diagram, a package named “System”, 
is where the component references from the library have the interfaces connected 
together.

By leaving the interfaces disconnected in the library, you are free to create 
other components and system wirings that connect the component references from 
the library together in different configurations.
