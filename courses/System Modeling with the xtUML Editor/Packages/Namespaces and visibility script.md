Packages have visibility properties that enforce how the data inside the package 
can be accessed by elements within, nested under, or outside the package. 
Packages support public (the default), protected, and private visibility. On the 
UI canvases, the package name is preceded by an indicator to show the current 
visibility setting: + (public), - (private) and # (protected).

Name-spacing is supported and managed entirely by means of visibility. That is, 
two elements with the same name are permitted provided that they are not 
simultaneously public in any action language scope. More than one type found 
during parsing is indicated by a parse error.

Note that changing the visibility of a container has no effect on the visibility 
setting of a child. If a package is visible to another element, it will be 
descended, regardless of the visibility setting. You may wonder: “So, what is 
the point of marking a package as private?” It is in the opposite conclusion; if 
a package cannot be seen, it will not be descended.

The behavior is closely analogous to that a text based programming language. For 
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

TODO - Discuss the visibility matrix