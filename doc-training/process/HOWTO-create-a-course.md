HOWTO Create a Training Course
============

1. Abstract
-----------
This document describes how to create an xtUML training course.  Our current course delivery 
platform (aka learning management system or LMS) is a WordPress plugin called WP Courseware 
that is integrated into xtuml.org.  We rely heavily on youTube for video hosting and the 
course content is archived and configuration managed here on github.

2. Document References
----------------------
[1] Banner, https://github.com/xtuml/training/blob/master/doc-training/process/templates/banner.xcf  
[2] Page template, https://github.com/xtuml/training/blob/master/doc-training/process/templates/Page_template.md  
[3] Simple Quiz template, https://github.com/xtuml/training/blob/master/doc-training/process/templates/Simple%20Quiz%20template.md  
[4] Camtasia Video Production Settings, https://github.com/xtuml/training/blob/master/doc-training/process/templates/HQ%20mp4%20@720p.xml  
[5] xtUML PowerPoint Template (16x9), https://github.com/xtuml/training/blob/master/doc-training/process/templates/xtUML_ppt_Template_16x9.potx    
[6] TubeChop, http://www.tubechop.com

3. Process
----------------------
The process of creating and running a course falls to two different categories of teachers: administrators and 
developers.  Anyone in the world can submit content as a course developer.  Course administrators actually create
and deliver the course using the learning management system.  
 
### Step 1 - Initialize the Course (course administrator)
  - Create a course project in the github `xtuml/training` repository
  - Create new course on http://xtuml.org
    - Open the xtuml.org dashboard
    - In the left-hand navigation bar, choose `Training Courses > Add Course`
    - There is a "wizard" that guides you through the course creation process, follow it to get the course skeleton created.

### Step 2 - Outline the Course Content (course administrator)
  - Create a course outline and save it to the course project directory on github.  The outline 
  should consider the top-level breakdown of the course into modules.  There will be individual 
  pages within each module.  Our general rule is to plan for a quiz at the end of each module.

### Step 3 - Add Course Modules (course developer)
  - Create folder structure on github in the course project for the module being developed

### Step 4 - Create Module Content (course developer) 
  - Create one or more videos for the units (topics) within the module. Here are some specific points to note when creating a video:
    - Use GPS Watch as much as possible
    - If your video will use PowerPoint slides, use the template we have [5] for consistency with other videos
    - All models used should be available in the xtuml/models repository
    - Keep video segments to 3 mins or less (if you are struggling with this limit, ask for input from the team)
    - Prefer real world abstractions.  (e.g. Use ```dog * --- * dog owner``` over ```foo * --- * bar```)
    - Use recording window dimensions that scale to 16x9 cleanly, likely 1280x720 or 1024x576
    - Consider using zooming in the recording or editing tool to focus in on a key area
    - When performing actions, do them as a new user would, not advanced user shortcuts
    - If you are using Camtasia Studio, we have a production preset file [4] that should be used.  Download this file
    and put it in ```C:\Users\kbrown\Documents\Camtasia Studio\Custom Production Presets 8.0``` substituting your username
    for ```kbrown``` of course.
  - Have the video reviewed by at least 2 members of the team
  - Pass the video to Dean McArthur or Keith Brown to upload it to youTube xtUML organization
  - Create a page using page template [2] for each unit video inside the module directory created in step 3
    - Explain the topic in the text
    - Link to the youTube video
    - Commit the page content file to github
    - If the unit will not have a new video but use a snippet from an existing video on YouTube you can use TubeChop [6]
    to specify the start and end points of the snippet.  Use the embedding html TubeChop gives you in the container 
    page.  Edit the dimensions (in 2 places of the embedding code to 640x360).
    - Notify course administrator of new page.  Course admin will create new page in the LMS and paste in page content
    from github.
    
### Step 5 - Create Module Quiz (course developer)
  - Create quiz content in text form.  You may want to use the Simple Quiz template [3].  Commit the quiz content github
  in the module directory created in step 3.

### Step 6 - Insert Module Content into Course (course administrator)
  - In WP Courseware, use `Training Courses > Add Module`.  Enter the relevant details.
  - Go to the course summary page, then click `Modules, Units, & Quiz Ordering` for the course that is being edited.
  - In the left-hand navigation bar, use `Course Units > Add New`.  Add a new unit for each page the developer created 
  that now lives in github.  Paste the raw HTML from github into the "Text" view of the page in WP Courseware.
  - Create a `<Module Name> - Conclusion` page.  This will hold the quiz later on.
  - In the left-hand navigation bar, use `Training Courses > Add Quiz/Survey`.  Using the content from the quiz stored
  in github for the module, create the quiz questions.
  - Go to the course summary page, then click `Modules, Units, & Quiz Ordering` for the course that is being edited.
  - Drag the units in the desired order from the right-hand "Unassigned" area into the appropriate module.  Put the 
  "Conclusion" unit last.
  - Drag the quiz into the module conclusion unit.
