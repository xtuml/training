HOWTO Create a Training Course
============

This document describes how to create an xtUML training course.  Our current course delivery 
platform is openlearning.com.  We rely heavily on youTube for video hosting and the course
content is archived and configuration managed here on github.

### Step 1 - Initialize the Course 
  - Create a course project in the github ```xtuml/training``` repository
  - Create new course on http://openlearning.com
    - There is a "wizard" that guides you through the course creation process, follow it
    - Note that to set an entirely self-paced course, follow these steps:  Select 'self-paced' on ```Teacher Access > Timeline``` 
    and then remove the start date from the Class by going to ```Administrator Access > Content > Date Settings``` and remove 
    the start date. That way the modules and activities won't have dates associated with them and it will just be self-paced. 
    - Create a badge graphic for course completion, configure it for use on ```Administrator Access > Community``` page

### Step 2 - Outline the Course Content
  - Create a course outline and save it to the course project directory on github.  The outline should consider the top-level
  breakdown of the course into modules.  There will be individual pages within each module.  The course outline should also
  indicate points at which users should be quizzed to check their learning retention.

### Step 3 - Add Course Modules
  - Create folder structure on github
  - Create new modules in open 
  
### Step 4 - Add Course Pages 
  - Create a video for the page/topic.  Pass the video to Dean to upload it to youTube xtUML organization
  - Create page using page template
    - Explain the topic in the text
    - Link to the youTube video
    - Commit the page content file to github
    - Create new page on openlearning, paste in page content
    
### Step 5 - Create Module Quiz
  - Create quiz content in text form, commit to github
  - Create new quiz activity on openlearning, build up quiz using content created previously

### Step 6 - Publish the Course
  - On openlearning, set the source to "Online" on ```Administrator Access > General```
  - Publish a note on xtUML.org that the course is now available