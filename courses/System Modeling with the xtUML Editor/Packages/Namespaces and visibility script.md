Packages have visibility properties that enforce how the data inside the package 
can be accessed by elements within, nested under, or outside the package. 
Packages support public (the default), protected, and private visibility. On the 
UI canvases, the package name is preceded by an indicator to show the current 
visibility setting: + for public, - for private and # for protected.

Name-spacing is supported and managed entirely by means of visibility. That is, 
two elements with the same name are permitted provided that they are not 
simultaneously public in any action language scope. If there is a name collision, 
it is indicated with a parse error.

It is important to note that changing the visibility of a container has no effect 
on the visibility setting of a child. If a package is visible to another element, 
it will be descended, regardless of the visibility setting. You may wonder: “So, 
what is the point of marking a package as private?” It is in the opposite 
conclusion; if a package cannot be seen, it will not be descended.

The behavior is closely analogous to that of a text based programming language. For 
example, can you see public members of a private class in Java? Yes, but only if 
you are in the same package as that class. In fact, if you are not in the same 
package, you can't see the class, let alone its members. Here, the visibility of 
the container does not affect the visibility of its members.

In the default workspace configuration with inter-project references turned off, 
a consequence of the rule above is that marking a top level package as private is 
meaningless, since there is nothing above it to be hidden from. However, if the 
workspace has inter-project references turned on, top level package visibility 
does matter because it allows you to control which packages can be seen (and 
hence descended in searches) from other projects.

The xtUML Style Guide includes a visibility matrix on page 16.  It is available
inside the tool via ```Help > Help Contents > BridgePoint UML Suite Help > Reference".

TODO - Discuss the visibility matrix

