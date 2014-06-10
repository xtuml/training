Now it's time to create your first full-fledged enhancement to xtUML Editor.

Task:
  - Create a new context menu entry that inspects a Package and lists the Packages and Components inside it.
  
Jump Start:
  - There are several menu-based tools already implemented in ```com.mentor.nucleus.bp.utilities```, use them for reference.
  - Copy ```CheckModelIntegrity.java``` to the Java ```src``` package ```com.mentor.nucleus.bp.utilities.data```, then rename 
  the file to ```ListPackageContents.java``` and let Eclipse update references.
  - Open ```plugin.xml```, find the ```objectContribution``` block for CheckModelIntegrity.  Copy this block, paste it, and 
  update the new block for the new name ```ListPackageContents```.
  - Open ```ListPackageContents::run()```, note how it performs some actions then reports via a dialog. Replace the internals 
  of ```run``` with your own code that selects the Package and Component children and builds a string with their names. Display 
  the string in a dialog. 
