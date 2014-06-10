The xtUML Editor JUnit test cases require some special configuration in order to run successfully.  Due to the functionality of the screen manipulations and screen comparisons, some of the tests only run on Windows.  

Some additional configuration of the development environment is necessary to run the JUnit tests.

- Open Git Repository Exploring perspective.  Select the button to _Clone a Git Repository and add the clone to this view_
  - Using the wizard as performed previously, clone ```https://github.com/xtuml/models.git``` to a local repository ( _Example:  c:/git/xtuml/models_)

- Open ```c:/MentorGraphics/xtUMLEditor/eclipse/Launcher.bat``` in a text editor
  - After the ```set BP_JVM=...``` line add the following (adjusted for your previously chosen repository locations)

```
set XTUML_TEST_MODEL_REPOSITORY=C:/git/xtuml/models/test/
set XTUML_DEVELOPMENT_REPOSITORY=C:/git/xtum/editor
```

- Prepare to run unit tests (on MS Windows):
  - Exit xtUML Editor
  - Configure Windows Vista or Windows 7 for unit test running

```
      - Bring up the Windows Color and Appearance settings
        - Right click on the desktop background and select Personalize
        - In Vista select the Windows Color and Appearance hyperlink
        - In Windows 7 select the Windows Color hyperlink
        - In the window that appears, change the following attributes:
          - Active Title Bar    Size: 25 Font: Trebuchet 10
          - Border Padding      Size: 0
          - Caption Buttons     Size: 25
          - Icon                Size: 32 Font: Tahoma 8
          - Inactive Title Bar  Size: 25 Font: Trebuchet 10
          - Menu                Size: 19 Font: Tahoma 8
          - Message Box                  Font: Tahoma 8
          - Palette Title       Size: 17 Font: Tahoma 8
          - Selected Items      Size: 19 Font: Tahoma 8
          - Tooltip                      Font: Tahoma 8
        - If you have a smaller screen or resolution potential you may need to
          configure the start menu to not always be on top, or set it to auto-hide.
        - Note: Do NOT use the Windows setting that scaling text to make it easier to see. 
              This setting, in Windows 7, is found here:
              Personalize > Display > "Make it easier to read what is on your machine"
              That setting must be set to "smaller" 100%
              It is is adjusted your graphical compare restuls will not match,
              
        It is recommended to save this modified theme to make it easier to switch back to 
        at a later time.
```

  - Launch xtUML Editor

- Set the unit test history to assure the test summary tool capture all results
  - Open the Junit view
  - Select the drop-down arrow in the upper-right of the view
  - Select the History... option
  - Set "Maximum count of remembered test runs" to 30 

<hr style="color: #cccccc;" />

<table>
<tbody>
<tr>
<td><a style="color: #4183c4;" href="http://creativecommons.org/publicdomain/zero/1.0/"><img src="https://camo.githubusercontent.com/c5160f944848828fa33126d9a697e9abe43ea98f/687474703a2f2f692e6372656174697665636f6d6d6f6e732e6f72672f702f7a65726f2f312e302f38387833312e706e67" alt="CC0" data-canonical-src="http://i.creativecommons.org/p/zero/1.0/88x31.png" /></a></td>
<td>
<p style="font-size: 11px;">To the extent possible under law, the person who associated CC0 with this work has waived all copyright and related or neighboring rights to this work.</p>
</td>
</tr>
</tbody>
</table>