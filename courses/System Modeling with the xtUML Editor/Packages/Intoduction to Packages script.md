Packages group and organize the pieces of the model. They have no semantic 
meaning other than control of visibility. 

```
DEMO - Draw a package couple of packages (Analysis with subpackages, Use 
Cases, Sequences, Library - Hardware, Library - HAL, System - Test, 
System - Implementation)
```

Packages may contain many different types of elements, including sub-
packages.  These features allow you use packages for storage, access control, 
configuration management, and constructing libraries of reusable model 
fragments. 

Let's discuss some tips and best practices aimed at effectively employing
packages.

Our first guideline is to “document as you go” by entering description
information about each package you create when you create it. All too often 
analysts choose not to perform this step, surmising that they will circle 
back and add it later. This second pass to write the documentation rarely 
happens, and it is not surprising. The original ideas become stale or lost. 
The pressures of the later phases of the project outweigh a documentation 
pass. The size of the data to document often becomes so large, that the task seems 
insurmountable. Or, the original creator of the model elements has moved 
on to other work. 

Next, let's discuss package organization. Packages are required in two places: 
at the top level of a project and inside a component. A package will be the 
first model element you draw when starting a fresh project. This is because 
you must have a package to put other model elements in.  

And just like at the project level, packages are required at the component 
level.  You must organize the model elements inside components (the component 
internal behavior) into packages.  So, once you have navigated inside a 
component, create one or more packages first, then add the component internal model 
elements to these packages.

Aside from these requirements, there are no hard and fast rules 
about where packages, either for Analysis or Executable modeling, should 
go in the hierarchy. We simply recommend that related packages should 
be grouped, following the rules of cohesion. That is, maximize close proximity 
of related subject matter and minimize package interdependency.

The final guideline we'll discuss now is: use separate packages for libraries 
and system configurations.

```
DEMO - Let's look at an example. Here we have created a package that is a library 
of components which model hardware functionality. We have another package that 
is a library of components that serve as the hardware abstraction layer. Another 
package that is a library of components that serve as a test bench for the 
components elsewhere in the model. A package that contains the application 
itself. We have also created a package to contain the interfaces that the various 
components expose.  In each of our library packages, the component interfaces 
are specified, but the interfaces are intentionally left disconnected.

In this example, we created packages that define scenarios for how the system 
is wired together using component references.  For example, we have a system
package that connects an hardware component to a test driver component.  We also 
have a system implementation package that connects the same hardware component to
a hardware driver component instead of the test component.  Using library packages and 
component references in system configuration packages makes this possible.
```

The tool allows you to wire together components but this is strongly discouraged. Stick 
to creating component libraries using packages, and only wiring together component 
references in separate system configuraiton packages.

By leaving the interfaces disconnected in the library, we are free to create 
other components and system wirings that connect the component references from 
the library together in different configurations.

If you use a model compiler, it will allow you to specify exactly which wired system
implementation package you want to translate into target code.
