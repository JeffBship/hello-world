Specifically for NetBeans, the process to create and run this as a project is as follows:
1. Clone a local copy of the repository.
2. Create a new project in NetBeans: File-> New Project, Java, Java Application.
3. Within the "Source Packages" folder of the newly created project, copy the folders 
~\GrovePi\Projects\java\ButtonRotaryObserver\Project\grovepi\buttonrotarydemo
~\GrovePi\Projects\java\ButtonRotaryObserver\Project\grovepi\observer
4. The project uses the other GrovePi packages through jar files.  The NetBeans project must be pointed to the correct jar files.

   a. Right click the project name and select "Properties".
   b. In the Categories tree on the lest, select "Libraries".
   c. Click "Add JAR/Folder"
   d. Navigate to ~\GrovePi\Projects\java\ButtonRotaryObserver\Project\grovepi\observer and select each of the  jar files there, grovepi.jar and pi4j.jar.   *Note: This step must be repeated after moving the project to a different platform (ie moving it to the pi) due to different file structures.*
   e. Click OK to accept changes.
  
5. Run the file ButtonRotaryDemo. 
