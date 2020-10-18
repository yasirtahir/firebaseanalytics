### Google Analytics Codelab
This repo contains many files. Please go through this Readme and follow all the steps in order to implement Google Analytics in your Android Application. In order to save time, I have attached herewith the quick start project. Let's start?
### Getting Started
Download the .zip file and open the project in the Android Studio. If you face any issues, please raise your concerns.

### Before you begin
The following steps has been completed already for you but It's worth mentioning.

### **Step 1**: Create a Firebase project
Before you can add Firebase to your Android app, you need to create a Firebase project to connect to your Android app. Visit [Understand Firebase Projects](https://firebase.google.com/docs/projects/learn-more) to learn more about Firebase projects.
### **Step 2**: Register your app with Firebase
To use Firebase in your Android app, you need to register your app with your Firebase project. Registering your app is often called "adding" your app to your project.
1.  Go to the  [Firebase console](https://console.firebase.google.com/).
    
2.  In the center of the project overview page, click the  **Android**  icon (plat_android) or  **Add app**  to launch the setup workflow.
    
3.  Enter your app's package name in the  **Android package name**  field.
4. _(Optional)_ Enter other app information: **App nickname** and **Debug signing certificate SHA-1**.
5. Click **Register app**.

### **Step 3**: Add a Firebase configuration file
Add the Firebase Android configuration file to your app:

1.	Click  **Download google-services.json**  to obtain your Firebase Android config file (`google-services.json`).
2.  Move your config file into the module (app-level) directory of your app.
3. To enable Firebase products in your app, add the [google-services plugin](https://developers.google.com/android/guides/google-services-plugin) to your Gradle files.
4. In your root-level (project-level) Gradle file (`build.gradle`), add rules to include the Google Services Gradle plugin. Check that you have Google's Maven repository, as well.




