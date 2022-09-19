
# Day 2

This is Day 2 of building an AR application using Unity3D and Vuforia Engine. 
All the material and codes of this WORKSHOP are in there respective branches.

## Contents
- [About the Project](#about-the-project)
- [Vuforia](#vuforia)
- [Unity and Vuforia Integration](#unity-and-vuforia-integration)
- [AR Business Card](#ar-business-card)
- [Building for Android](#building-for-android)



## About the Project
We will be making an AR Business Card application deployed on android using Unity 3D and Vuforia. 
 
 You’re at a networking event. You hand your business card to someone. They add it their stash of business cards. You never hear from them again. Repeat.

An augmented reality business card is an ideal solution to this problem, not just because of its “wow” effect, but also because of its utility and convenience. 

We will be building the application such that scanning a business card(image target) shows videos, pictures, 3D Models, contact information, buttons and links to appropriate sites. In addition to this we will use animations in Unity 3D to make it more visually appealing.

### Built with
C#

## Vuforia
Vuforia Engine is a software development kit (SDK) for creating Augmented Reality apps. With the SDK, you add advanced computer vision functionality to your application, allowing it to recognize images, objects, and spaces with intuitive options to configure your app to interact with the real world.  

Vuforia Engine supports AR app development for Android, iOS, Lumin, and UWP devices. 

_For more details, visit [Vuforia documentation](https://library.vuforia.com/getting-started/getting-started-vuforia-engine-unity)_

### Unity and Vuforia Integration
- Create an account on Vuforia
- Login 
- Go to downloads and download the latest version of Vuforia engine 
- Import it in unity
    - You can either drag and drop it 
    or 
	- Right click on the project panel 
    - Click on 'Import package' 
    - Click on Custom package 
    - Navigate to the vuforia package you just installed
    - Then click on import
- Go to the Hierarchy panel
- Create the AR Camera object and Image target object by
    - Right click and choose the Vuforia Engine and select the AR Camera then again right click and choose the Vuforia Engine and select the Image target.
- Then go to the develop section in the vuforia portal (Browser)
- Under License manager
	- Get basic license 
	- Copy the license key 
	- Open unity and click on the AR Camera object then in the Inspector panel click on 'Open Vuforia Engine Configuration' under Vuforia Behaviour(Script) 
	- Then paste the license key in the app license key textbox (Dont click on the add license) 
- Under Target manager
    - Click on add database 
	- Enter database name and select the device option 
	- Then select the database
	- Add target (Type: Image, Width: 6, Unique name)
	- Rating indicates how augmentable our image is.
	- If you select the target you can see the details and if you click on show features you can check the features which are making the target unique.
	- After that download the database and select the 'Unity Editor' and download it.
- Import the database package in unity
- Then select the Image target and choose 'from database' option under type
- Then select the database you just imported under the Database 
- Then select the Image target we uploaded to Vuforia 

## AR Business Card

- Start with Unity and Vuforia Integration
- Change the build settings to Android.
- Create an Image target in the Hierarchy Panel (Business Card)
- Add a Canvas object and make it child of Image Target. Make the Render mode to World Space and drag AR Camera into event camera.
- Add a Panel game object and drag your related video into the Inspector panel. Resize accordingly, and the video should be played in Game Mode
- All the images imported in Unity should be of texture type Sprite(2D and UI). You can do that in the Inspetor panel.
- Add image and text game objects, resize an change components accordingly.
- Add button and scale it accordingly, you can delete the text component. Add aprropriate image to the button.
- In assets, create a new c# Script, and add the script to a new Empty game object. Rename it to Scripts
- Function code for buttons:
    ```
    void fuction_name() {
    Application.OpenURL("url");
    } 
    ```
- Save the Script
- Add Onclick Event listener in the inspector panel of button.
- Drag the Scripts object into Onclick, and add the required Function.(the void function_name which yu defined)
- Entering Game Mode, the scanned image target (Business card) should display the video, images, text and buttons. On clicking the buttons it should open the URL in browser.

### Building for Android
- In Build Settings -> Player settings, select the Minimum API Level as 26 (Android Oreo)
- Click Build , and an .apk file should be created.
- Transfer it to android mobile, and your AR Business Card application should be ready to use.
