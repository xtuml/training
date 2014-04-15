HOWTO Create a Training Course
============

1. Abstract
-----------
This document describes how to create an xtUML training course.  Our current course delivery 
platform is openlearning.com.  We rely heavily on youTube for video hosting and the course
content is archived and configuration managed here on github.

2. Document References
----------------------
[1] Banner, https://github.com/xtuml/training/blob/master/doc-training/process/templates/banner.xcf  
[2] Page template, https://github.com/xtuml/training/blob/master/doc-training/process/templates/Page_template.md  
[3] Simple Quiz template, https://github.com/xtuml/training/blob/master/doc-training/process/templates/Simple%20Quiz%20template.md  

3. Process
----------------------
The process of creating and running a course falls to two different categories of teachers: administrators and 
developers.  Anyone in the world can submit content as a course developer.  Course administrators actually create
and deliver the course using the learning management system.  
 
### Step 1 - Initialize the Course
  - Create a course project in the github ```xtuml/training``` repository
  - Create new course on http://openlearning.com
    - There is a "wizard" that guides you through the course creation process, follow it to get the course skeleton created
    - Course banner template (GiMP format) can be found at [1]
    - Note that to set an entirely self-paced course, follow these steps:  Select 'Self-Paced' on ```Teacher Access > Timeline``` 
    and then remove the start date from the Class by going to ```Administrator Access > Content > Date Settings``` and remove 
    the start date. That way the modules and activities won't have dates associated with them and it will just be self-paced. 
    - Create a badge graphic for course completion, configure it for use on ```Administrator Access > Community``` page

### Step 2 - Outline the Course Content
  - Create a course outline and save it to the course project directory on github.  The outline should consider the top-level
  breakdown of the course into modules.  There will be individual pages within each module.  The course outline should also
  indicate points at which users will be quizzed to check their learning retention.

### Step 3 - Add Course Modules
  - Create folder structure on github in the course project for the modules
  - Create new corresponding modules in the openlearning course 
  
### Step 4 - Add Course Pages 
  - Create a video for the page/topic.  Pass the video to Dean McArthur or Keith Brown to upload it to youTube 
  xtUML organization.  Here are some specific points to note when creating a video:
    - Use GPS Watch as much as possible
    - All models used should be available in the xtuml/models repository
    - Keep video segments to 3 mins or less (if you are struggling with this limit, ask for input from the team)
    - Prefer real world abstractions.  (e.g. Use ```dog * --- * dog owner``` over ```foo * --- * bar```
    - Use recording window dimensions that scale to 16x9 cleanly
    - Consider using zooming in the recording tool to focus in on a key area
    - When performing actions, do them as a new user would, not advanced user shortcuts
  - Create page using page template [2]
    - Explain the topic in the text
    - Link to the youTube video
    - Commit the page content file to github
    - Notify course administrator of new page.  Course admin will create new page on openlearning, paste in page content
    from github.
    
### Step 5 - Create Module Quiz
  - Create quiz content in text form.  You may want to use the Simple Quiz template [3].  For game quizzes (crosswords,
  fill in the blank, category sort) we do not have a template.  Commit the quiz content github.
  - Create new quiz activity on openlearning, build up quiz using content created previously

### Step 6 - Publish the Course
  - On openlearning, set the source to "Online" on ```Administrator Access > General```
  - Publish a note on xtUML.org that the course is now available
