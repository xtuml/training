Packages group and organize the pieces of the model. They have no semantic 
meaning other than control of visibility. 

DEMO - Draw a package couple of packages (Analysis with subpackages, Use 
Cases, Sequences, Library - Hardware, Library - HAL, System - Test, 
System - Implementation)

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

Next, let's discuss package organization. There are no hard and fast rules 
about where packages, either for Analysis or Executable modeling, should 
go in the hierarchy. We simply recommend that related packages should 
be grouped, following the rules of cohesion. That is, maximize close proximity 
of related subject matter and minimize package interdependency.

The final guideline we'll discuss now is: use separate packages for libraries 
and system wirings. You should create packages that serve as libraries of 
components. For example, create a package that is a library of components which 
models hardware functionality. Create another package that is a library of components that 
serve as the hardware abstraction layer. Create another package that is 
a library of components that serve as a test bench for the components elsewhere 
in the model. Create another package or packages that contain the application 
itself. You can also create packages to contain the interfaces that the various components 
expose. Then, create one or more packages that define scenarios for how the system 
is wired together using component references.  For example, you may have a system
package that connects an hardware component to a test driver component.  You could 
then have a system implementation package that connects the same hardware component to
a hardware driver component instead of the test component.  Using component references 
in system wiring packages makes this possible.

The tool allows you to wire together components but this is strongly discouraged. Stick 
to creating component libraries using packages, and only wiring together component 
references in separate system implementation packages.

DEMO - Let's consider an example using the GPS Watch case study project included 
in the xtUML Editor help. Here we see a "Library" package that contains the 
components. The component interfaces are specified, but the interfaces are 
intentionally left disconnected. The wiring diagram, a package named “System”, 
is where the component references from the library have the interfaces connected 
together.

By leaving the interfaces disconnected in the library, we are free to create 
other components and system wirings that connect the component references from 
the library together in different configurations.

If you use a model compiler, it will allow you to specify exactly which wired system
implementation package you want to translate into target code.
