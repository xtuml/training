---

CC0

---

# Self-Paced Training Content
### xtUML Project Design Note


1. Abstract
-----------
As part of a larger strategy to improve the available xtUML education a
set of online, self-paced training materials are prepared.  These materials
will be open, accessible, extensible, growing, indexed and searchable.
A starting outline of the materials is presented here.

2. Document References
----------------------
[1] Issues 1, https://github.com/xtuml/doc/issues/1 -
    Outline Self-Paced Course  
[2] Issues 166, https://github.com/xtuml/internal/issues/166 -
    xtUML Self-Paced Course  
[3] ClearQuest Issue:  dts0101037429
    Outline Self-Paced Course  
[4] Issues 141, https://github.com/xtuml/internal/issues/141 -
    Analyze xtUML Training  
[5] CQ dts0101022089 - Analyze an Improved BridgePoint Training Class  


3. Background
-------------
The world expects to learn how to use engineering development tools online
and on the terms of the user.  "Show me."  In 2014, the most common medium
has become video stored and indexed on YouTube.

4. Requirements
---------------
See [4] and [5].

5. Analysis
-----------
See [4] and [5].

6. Design
---------
6.1       Installation  
6.1.1     Installing xtUML Editor  
6.1.1.1   Installing xtUML Editor on Linux  
6.1.1.2   Installing xtUML Editor on Windows  
6.1.2     Installing BridgePoint  
6.1.3     Installing Source Model Compilers  
6.2       Workspaces:  Creating and Switching  
6.2.1     Eclipse and Eclipse Terms  
6.2.1.1   Workspace, Project, Resource, View, Editor, Perspective  
6.3       xtUML Projects  
6.3.1     Interproject References (IPRs) 
6.3.1.1   Shared Data Types and Constants  
6.3.1.2   Shared Interfaces  
6.3.1.3   Shared Components  
6.3.1.4   Shared External Entities  
6.3.1.5   Synchronizing References  
6.3.2     Library Projects (definitions)  
6.3.3     Integration Projects (system configurations) 
6.4       Import and Export  
6.5       Packages:  Creating, Nesting, Organizing  
6.6       Components and Interfaces  
6.6.1     Interfaces  
6.6.2     Messages:  Signals and Operations 
6.6.2.1   Message direction  
6.6.2.2   Message parameters  
6.6.2.3   Return value (Operations) 
6.6.3     Components  
6.6.4     Ports 
6.6.4.1   Port activities (incoming and outgoing messages)  
6.6.4.2   Component reference (sender keyword) 
6.6.5     Component References, Interface References and Port References  
6.6.6     Nesting Components  
6.6.7     Port/Interface/Message Delegation  
6.6.8     Organizing Component, Interface, Data Type Definitions into Library Packages  
6.6.9     System configuration packages
6.7       Class Diagram  
6.7.1     Editing a Class 
6.7.1.1   Instance-based operations
6.7.1.2   Class-based operations 
6.7.2     Performing a Class Blitz  
6.7.3     Placing Attributes with Data Types  
6.7.4     Associations  
6.7.4.1   Simple Associations  
6.7.4.2   Multiplicity and Conditionality (Cardinality)  
6.7.4.3   Labeling and Reading Associations Correctly  
6.7.4.4   Reflexives  
6.7.4.5   Associative Classes (Ternary Associations)  
6.7.4.6   Generalization:  Subtypes and Supertypes (Not Inheritance)  
6.7.5     Imported Classes (Class References, Off-Page Connections)  
6.7.6     Steps to Creating Class Diagrams  
6.8       State Modeling  
6.8.1     Basics of States, Transitions, Events and Actions  
6.8.2     Instance State Machines versus Class-Based State Machines  
6.8.3     Instance State Models  
6.8.4     State Event Matrix  
6.8.5     Final States, Initial State (lowest numbered state) and Creation Events  
6.8.5.1   Synchronous Creation  
6.8.5.2   Asynchronous Creation  
6.8.6     Class-Based State Models  
6.8.6.1   Assigning an Interface Signal to a Transition  
6.8.7     Timers (Delayed Events)  
6.8.8     "Polymorphic Events" (Asynchronous polymorphism)  
6.8.9     Steps to Creating a State Model  
6.9       Action Language  
6.9.1     Overview  
6.9.2     Setting up the Workspace  
6.9.3     Creating an Action Language Function  
6.9.4     Editing Hello World  
6.9.5     Running Hello World  
6.9.6     Action Language Data Types  
6.9.7     Simple Arithmetic  
6.9.8     If Statements  
6.9.9     While Loops  
6.9.10    Calling Functions  
6.9.11    Creating Instances of Classes and Initializing Attribute Values  
6.9.12    Deleting Instances of Classes  
6.9.13    Selecting Any Instances and Checking for Empty References  
6.9.14    Selecting Instances using the Where Clause  
6.9.15    Relating Instances Across Associations using Relate Statement  
6.9.16    Selecting One Instance and Unrelate Statement  
6.9.17    Selecting Many Instances and Iterating using For Each  
6.9.18    Action Language Homes  
6.9.19    Generating State Machine Events  
6.9.20    Generating Events to Class-Based State Machines 
6.9.21    Generating Creation Events  
6.9.22    Creating Event Instances (for Timers)  
6.9.23    Navigating Reflexive Associations  
6.10      Activity Diagrams  
6.10.1    Activity Symbols  
6.11      Communication Diagrams  
6.11.1    Communication Symbols  
6.12      Use Cases  
6.12.1    Use Case Symbols  
6.13      Sequence Diagrams  
6.13.1    Sequence Symbols  
6.14      Configuration Management  
6.14.1    Model Compare  
6.14.2    Model Merge  
6.14.3    Git and GitHub  
6.14.4    Models, Documents and Source Code on GitHub  
6.15      eXecuting Models (Verifier)  
6.15.1    Launch Configurations 
6.15.1.1  Simulated Time, Clock Time, Run Deterministically, Logging  
6.15.1.2  Enabling Instance Population Checks 
6.15.2    Exploring the Session  
6.15.3.1  Browsing Instances and Attribute Values  
6.15.4.2  Traversing Links Between Instances  
6.15.5    Stopping, Starting and Single-Stepping  
6.15.6    Breakpoints  
6.15.7    Spotlight  
6.15.8    Simple Test Cases (functions)  
6.15.9    OAL Console (functions)  
6.16      Translating Models (Model Compilers)  
6.16.1    Choosing/Setting a Model Compiler  
6.16.2    Changing/Setting/Switching a Model Compiler  
6.16.3    Generating Code  
6.16.3.1  Marking  
6.16.4    Compiling the Generated Code  
6.17      Command Line Interface (CLI)  
6.17.1    Command Line Interface Overview  
6.17.2    CLI for eXecute (Verifier)  
6.17.3    CLI for Translate (Model Compiler)  
6.18      Model-Based Testing  
6.19      Realized Code Integration (Legacy Integration)  
6.19.1    Verifier Interface to External Code  
6.20      Cheat Sheets  
6.21      Building the xtUML Editor from Source  

7. Design Comments
------------------

8. Unit Test
------------

End
---

