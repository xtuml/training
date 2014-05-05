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
Owner:    Travis  
6.4       Fork editor to your github account  
```
```
Owner: 
6.5       Pull data to local repository and workspace  
6.5.1     Clone source from your account to your local machine using xtUML Editor. Emphasize
that we clone to a directory (repository) location _outside_ the workspace.  
6.5.2     Import Projects into workspace  
```
```
Owner: 
6.7       Build   
6.7.1     Build project  
6.7.2     Build automatically  
```
```
Owner: 
6.8       Running and Debugging    
6.8.1     Launch xtUML Editor launch config  
6.8.2     Run vs Debug  
6.8.3     Java Exception Breakpoints (Set NPE breakpoint)  
```
```
Owner: 
6.9       Exercise - Default Data Type  
6.9.1     Find where we set the default type for new attribute in OAL and Java.  Attribute
Class > Initialize(),  bp.core/Attribute_c.initialize()  
6.9.2     Change the default to "real"   
6.9.3     Show via breakpoint and stepping that the type successfully changed  
```
```
Owner: 
6.10      Select statements, OAL and Java   
6.10.1    Look at the traversal we want to do in the metamodel from attribute up to system  
6.10.2    Go to Attribute::Initialize() OAL line 39, see the select statement here    
6.10.3    Now look at how the selection is implemented in the java bp.core/Attribute_c.java:  
```
```
Owner: 
6.11      Export plug-in and put it into an Editor installation  
6.11.1    Look at the plug-ins in the xE installation.  See if the plug-in we want to export
is a directory or jar  
6.11.2    Use plugin.xml Export Wizard to export the plug-in  
6.11.3    Copy it in to the distribution  
```

Exercise possibilities:
- Create a new plug-in that implements a builder that reads and exports model data
- Create a new plug-in that sucks in OAL from a file and injects it into the model at 
the right spot.  Use function.gen plugin as a base?


7. Design Comments
------------------

8. Unit Test
------------

End
---
