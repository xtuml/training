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
This section is only required if there is no preceding analysis note. 
If present it describes the requirements that need to be satisfied.  If there 
is an SRS, this section may simply refer to it.  Each requirement should be as 
short and simple as possible and must be clearly defined.

5. Analysis
-----------
See [4] and [5].

6. Design
---------
6.1       Installation
6.1.1     Installing xtUML Editor
6.1.2     Installing BridgePoint
6.1.3     Installing Source Model Compilers
6.2       Workspaces:  Creating and Switching
6.2.1     Eclipse and Eclipse Terms
6.2.1.1   Workspace, Project, Resource, View, Editor, Perspective
6.3       xtUML Projects
6.3.1     Interproject References (IPRs)
6.4       Import and Export
6.5       Packages:  Creating, Nesting, Organizing
6.6       Components and Interfaces
6.6.1     Interfaces
6.6.2     Messages:  Signals and Operations
6.6.3     Components
6.6.4     Ports
6.6.5     Component References, Interface References and Port References
6.6.6     Nesting Components
6.6.7     Port/Interface/Message Delegation
6.7       Class Diagram
6.7.1     Editing a Class
6.7.2     Performing a Class Blitz
6.7.3     Placing Attributes with Data Types
6.7.4     Associations
6.7.4.1   Simple Associations
6.7.4.2   Multiplicity and Conditionality (Cardinality)
6.7.4.3   Labeling and Reading Associations Correctly
6.7.4.4   Reflexives
6.7.4.5   Associative Classes (Ternary Associations)
6.7.4.6   Generalization:  Subtypes and Supertypes (Similar to Inheritance)
6.7.5     Imported Classes (Class References, Off-Page Connections)
6.7.6     Steps to Creating Class Diagrams
6.8       State Modeling
6.8.1     Basics of States, Transitions, Events and Actions
6.8.2     Instance State Machines versus Class-Based State Machines
6.8.3     Instance State Models
6.8.4     State Event Matrix
6.8.5     Final States, Initial States and Creation Events
6.8.6     Class-Base State Models
6.8.7     Timers (Delayed Events)
6.8.8     "Polymorphic Events" (Event Inheritance)
6.8.9     Steps to Creating a State Machine
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
6.15.2    Exploring the Session
6.15.3.1  Browsing Instances and Attribute Values
6.15.4.2  Traversing Links Between Instances
6.15.5    Stopping, Starting and Single-Stepping
6.15.6    Breakpoints
6.16      Translating Models (Model Compilers)
6.16.1    Choosing/Setting a Model Compiler
6.16.2    Changing/Setting/Switching a Model Compiler
6.16.3    Generating Code
6.16.4    Compiling the Generated Code

7. Design Comments
------------------

8. Unit Test
------------

End
---





4. Requirements
---------------
4.1 Motivation  
4.1.1 There shall be collateral for a motivational presentation(s) that
explains and demonstrates the incentives for modeling with eXecutable
and Translatable UML.  
4.1.2 The above collateral will be deliverable by a live individual with
experience in xtUML to a live audience.  
4.1.3 There shall be a self-paced, recorded/electronic version of the
above presentation.  The self-paced version may have a lower effectiveness
than when presented live by an experienced xtUML modeler, but the
effectiveness must be high enough to guide motivated individuals with
a clear need and sufficient technical background.  

4.2 xtUML Modeling Course  
4.2.1 There shall be collateral for a live instructor-led class that includes:
- historical highlights to establish context
- theoretical background of executable modeling
- compelling, pedagogical case study
- exercises with solutions  

4.2.2 The above collateral shall be deliverable by a live individual with
experience in xtUML to a face-to-face audience.  
4.2.3 There shall be a self-paced, recorded/electronic version of the
above material.  The self-paced version may have a lower effectiveness
than when presented live by an experienced xtUML modeler, but the
effectiveness should be high enough to guide motivated individuals with
a clear need and sufficient technical background.  
4.2.4 Existing materials may be repurposed for the updated classroom
training.  
4.2.5 Low-level details of tool usage shall be omitted from the classroom
training.  This can be accomplished by pre- or post- requisite tool
training or some other equally effective means of enabling a focus on
theory, examples and exercises centered around modeling.

4.3 Self-Paced Tool Training  
4.3.1 There shall be collateral for on-line, electronic, self-paced
training courses.  
4.3.2 The self-paced courses shall focus on the mechanics of modeling using
the xtUML Editor and BridgePoint.  
4.3.3 Courses shall require student interaction through questions
and quizzing along the way.  
4.3.4 Courses shall be indexed to a fine granularity such that students
and modelers can use the material as a reference guide.  
4.3.5. The self-paced course shall be sequenced along one or more
task-oriented workflows that guide the student step-by-step to the
accomplishment of a typical and particular modeling task.  Workflows
will include at least:  
4.3.5.1 System Documentation Workflow  
4.3.5.2 Embedded Software Workflow  
4.3.5.3 Hardware Module Workflow  
4.3.5.4 System-Level Modeling Workflow  
4.3.5.5 Virtual Platform Workflow  
4.3.5.6 Test Workflow

4.4 Tracking, Grading and Evaluation  
4.4.1 Tracking of Students/Users  
4.4.1.1 Each student will be identified (perhaps by name and email address).
The material covered by the student will be recorded and retained for a
period of 1 year from last login.  
4.4.2 Responses supplied by students to questions will be recorded and
retrievable at a later date.  Response data will be retained for a period
of 1 year from last login.  
4.4.3 Each training segment will be accompanied by at least 1 graded quiz
question.  The focus of these questions will be engagement, information
retention, key point highlighting, progress feedback and progress tracking.  
4.4.4 A threshhold of correct responses will be required/recommended before
allowing a student to continue.  

4.5 Indexing and Referencing  
4.5.1 A "reference manual" of the training material will be viewable online
and be easily searchable.  xtUML Editor (and BridgePoint) users must be able
to find pointed "how-to"s for a good percentage of modeling tool tasks.

4.6 Involvment of the xtUML Community  
4.6.1 Online training collateral shall be easily extendible by members of
the xtUML Community.  
4.6.2 Additions will require no approval of a moderator.  
4.6.3 A moderator shall be able to remove or reclassify innapropriate or
incorrect materials.

4.7 Licensing  
4.7.1 xtUML course collateral shall be licensed under Creative Commons 1.0 (CC0).

4.8 Accessibility  
4.8.1 Training collateral shall be accessible through links from xtuml.org.  
4.8.2 Configuration management for final versions of collateral will be on
the open xtuml github.com repositories.  
4.8.3 Google/Bing/etc. searches will have visibility to the materials.  
4.8.4 Packaged materials can (also) live in access-controlled locations
commercially administered by Mentor Graphics.  

4.9 Salability  
4.9.1 These materials will be packageable for sale (by Mentor Graphics).  
4.9.2 Licensing will need to be reviewed to be compatible with Mentor
sales and licensing processes.  

4.10 Time Constraints
4.10.1 Recommended timing of course material shall be recommended to students.  
4.10.2 Reduced effectiveness due to deviation from these time constraints
shall be the responsibility of the student/(customer).  


5. Analysis
-----------

6. Work Required
----------------
6.1 [5] The base of this collateral exists in PowerPoint presentations and
videos.  Refinement and final production of this presentation will need
to assemble the available material.  Also, the material then needs to
be placed under CC0 and stored/linked on xtuml.org and github.

6.2 [6] The present materials will serve as the base for the new course.  
6.2.1 Update the slides to omit (most) references to tool specifics.  
6.2.2 Update the exercises to use pencil, paper and other tool non-
specific mechanisms.  
6.2.3 Rework the overall flow to include all of the key concepts needed
to enable learners to go from spec to model with understanding.  

6.3 [7]
6.4 [8]
6.5 [8]
6.6 [8]
6.7 [8]
6.8 [8]

6.9 Work together with Mentor Sales, SLE Marketing and CSD to ensure
materials can be packaged in a way that satisfies requirements for
legally selling them.

7. Acceptance Test
------------------

End
---

