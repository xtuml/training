---

CC0

---

# xtUML Editor Developer Training Content
### xtUML Project Design Note


1. Abstract
-----------
As part of a larger strategy to improve the available xtUML education a
set of online, self-paced training materials are prepared.  These materials
will be open, accessible, extensible, growing, indexed and searchable.
There will be several courses available.  A "user" course is outlined in [2]. Another
course for xtUML Editor Developers is outlined here.

2. Document References
----------------------
[1] Issues 5, https://github.com/xtuml/training/issues/5 -
    Outline xtUML Editor Developer Course  
[2] Issues 1, https://github.com/xtuml/training/issues/1 -
    Outline Self-Paced Course  

3. Background
-------------
We want to expand the xtUML Editor developer community.  To do this, we need to equip
interested parties with training to get their feet wet and learn how to begin modifying 
the xtUML Editor.

4. Requirements
---------------

5. Analysis
-----------

6. Design
---------
```
Owner: Keith
6.1       Installation  
6.1.1     Installing xtUML Editor  
6.1.1.1   Installing xtUML Editor on Linux  
6.1.1.2   Installing xtUML Editor on Windows  
```
```
Owner: 
6.2       Create account on github
```
```
Owner: 
6.3       Download and install add-ons file
```
```
Owner: 
6.4       Fork editor to your github account  
```
```
Owner: 
6.5       Clone source from your account to your local machine using xtUML Editor
```
```
Owner: 
6.6       Import Projects
```
```
Owner: 
6.7       Build
```
```
Owner: 
6.8       Exercises
```
```
Owner: 
6.9       TODO
```

Exercise possibilities:
- Create a new plug-in that implements a builder that reads and exports model data
- Create a new plug-in that sucks in OAL from a file and injects it into the model at 
the right spot.  Use function.gen plugin as a base?
- Use breakpoints to inspect the internals of the implementation of some feature
- Select statements with traversals.  Figuring out in the metamodel what the select 
looks like, then implementing it in code.

7. Design Comments
------------------

8. Unit Test
------------

End
---
