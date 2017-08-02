A number of xtUML model elements support the visibility property to enforce how the data inside them can be accessed by elements within, nested under, or outside the element. Visibility can be set to public (which is the default), protected, and private. On the UI canvases, the element name is preceded by an indicator to show the current visibility setting: + for public, - for private and # for protected.  Visibility control is especially useful in conjunction with packages to segregate model data and control access to internal behavior.

TODO - DEMO HOW TO CHANGE the VISIBILITY VIA THE CONTEXT MENU

Let's begin by talking about namespaces. Name-spacing is supported and managed entirely by means of visibility. That is, two elements with the same name are permitted provided that they are not simultaneously public in any action language scope. xtUML Editor does some checks when elements are created to help avoid name collisions.  In addition, the parser will indicate a parse error on any name collisions it finds.

Now, let's discuss the visibility rules.  The first point to understand is that changing the visibility of a container (that is, a package or a component) has no effect on the visibility settings of its children. Each nested child has its own visibility setting.  

The next point, and this can be tricky for some to understand, is that if an element is visible to another element, it will be descended, regardless of the visibility setting on the target element. Now you may wonder: “So, what is the point of marking a package as private?” It is in the opposite conclusion; if a package cannot be seen, it will not be descended.  The key is that setting a container to "private" restricts its visibility to some, _but not all_, other elements in the model.

The behavior is closely analogous to that of a text based programming language. For example: can you see public members of a private class in Java? Yes, but only if you are in the same package as that private class. If you are not in the same package, you can't see the private class, let alone its public members. In both the xtUML and Java scenario, marking the container (the xtUML package or the Java class) as private does not mean that its contents are entirely hidden from everyone in the outside world.  There are some elements that do still have access to the internals of the container, even though the container itself is marked as "private".  In the case of xtUML, the visibility rules define that peer elements fall into this category. Peers are always allowed to look inside one another, even if one or both of them is private.

For the purposes of this example, I have modifed a screenshot of the tool to show the internals of the node_pkg and probe_pkg packages, the internals of packages are not actually shown like this inside the tool.

Here we see rule #2 in action.  Since node_pkg is a peer of the pacer class, node_pkg is always visible to pacer even though it is marked private.  This means that OAL in pacer::findNodes() operation will search inside node_pkg when looking for named elements.  Then the individual visibility of the elements inside node_pkg comes into play.  Thus, OAL in pacer can "see" the node class, but cannot see the module class.

Using the same rules, node_pkg is not visible to the probe class.  Thus, OAL in probe can see the public pacer class one level up, but it cannot see node_pkg, and therefore cannot descend into node_pkg and see either class node or module.

In the default workspace configuration with inter-project references turned off, a consequence of the visibility rules is that marking a top level package as private is meaningless, since there is nothing above it to be hidden from. However, if the workspace has inter-project references turned on, top level package visibility does matter because it allows you to control which packages can be seen (and hence descended) from other projects.

The xtUML Style Guide includes the visibility matrix on page 16. The Style Guide is available inside the tool via ```Help > Help Contents > BridgePoint UML Suite Help > Reference".



