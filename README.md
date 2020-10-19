## Google Analytics Codelab
This repo contains many files. Please go through this Readme and follow all the steps in order to implement Google Analytics in your Android Application. In order to save time, I have attached herewith the quick start project. 
## Getting Started
Download the [.zip file](https://github.com/yasirtahir/firebaseanalytics/raw/main/FirebaseAnalytics_StarterCode.zip) and open the project in the Android Studio. If you face any issues, please raise your concerns.

## Before you begin (Optional)
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

Go to **allprojects** > **repositories** and configure the Maven repository address for the HMS Core SDK.

    buildscript { 
    
	    repositories {  
		    **// Check that you have the following line (if not, add it): 
		    google()  // Google's Maven repository**  
	    } 
	    
	    dependencies {  
		    // ...  
		    **// Add the following line: 
		    classpath 'com.google.gms:google-services:4.3.4'  // Google Services plugin**  
		}  
	}
	
	allprojects {  
	// ... 
	
		repositories {  
			**// Check that you have the following line (if not, add it): 
			google()  // Google's Maven repository**  
			// ...  
		}  
	}


In your module (app-level) Gradle file (usually `app/build.gradle`), apply the Google Services Gradle plugin:

    apply plugin:  'com.android.application'  
	**// Add the following line:  
	
	apply plugin:  'com.google.gms.google-services'  
	// Google Services plugin**
	
	android {  
		// ...  
	}

## Code Integration
The code that you downloaded, please build it and try to run it successfully on the emulator to check if everything is working fine or not. If yes, let's start writing our Analytics code.

**(Step 1.0)** Add app build dependencies.
```
// TODO: 1.0 Add Firebase Analytics dependencies here
dependencies {
	// leave all the previously added dependencies as it is
    implementation platform('com.google.firebase:firebase-bom:25.12.0')  
	implementation 'com.google.firebase:firebase-analytics-ktx'
}
```

**(Step 1.1)** Add the following related permissions to the **AndroidManifest.xml** file of your project.
```
<!-- TODO: 1.1 add Permissions here -->  
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />  
<uses-permission android:name="android.permission.INTERNET" />  
<uses-permission android:name="android.permission.WAKE_LOCK" />
```
**(Step 1.2)** Declare the FirebaseAnalytics object in the **MainActivity.kt** class as global variable

```
// TODO: 1.2 Add here the object at the top of MainActivity  
private lateinit var firebaseAnalytics: FirebaseAnalytics
```


**(Step 1.3)** Initiate the FirebaseAnalytics object in the **onCreate** method of MainActivity.kt
```
// TODO: 1.3 Initiate the object here  
// Obtain the FirebaseAnalytics instance.  
firebaseAnalytics = Firebase.analytics
```

**(Step 1.4)** Write the following code in the **sendEvent()** method declared in the MainActivity.kt
```
// TODO: 1.4 Add code for send event log  
firebaseAnalytics.logEvent("CustomEvent") {  
  param("developer_name", WRITE_NAME_HERE) // TODO: 1.5 Change the name to your Real Name  
  param("full_text", "This is a custom event sent from the mobile app")  
}
```


**(Step 1.5)** Write your name as the developer name as mention in the previous Step 1.4
```
param("developer_name", "WRITE_NAME_HERE") // TODO: 1.5 Change the name to your Real Name  
```

**(Step 1.6)** Call the sendEvent function inside the Click Event Listener
```
// TODO: 1.6 Call the function here to send event  
sendEvent() 
```

**That's Great!** We have completed all the steps and now ready to test our integration. If you are still facing any issues with the integration, please raise your hands. Please sync your code now and try to run it on the Emulator.

## Run the Application
Once you run the application, you will see the following:


![This is how the app looks like when we run after completing all the steps](https://github.com/yasirtahir/firebaseanalytics/raw/main/images/GoogleAnalytics.jpg)


## Real Time Visualization 
Now, I'll show you how to monitor real-time visualization on the Firebase Console.



## Validate your Analytics configuration with DebugView
Use DebugView to validate your Analytics configuration for apps during development.
To enable Analytics Debug mode on an emulated Android device, execute the following command line:

	adb shell setprop debug.firebase.analytics.app <package_name>

> In our case, write the package name com.yasir.firebaseanalytics

This behavior persists until you explicitly disable Debug mode by executing the following command line:

	adb shell setprop debug.firebase.analytics.app .none.

## Congratulations

Well done. You have successfully completed this codelab and learned how to:

-   Integrate Google Analytics.
-   How to Visualize the Data.

For more details, please refer to the  [Development Guide](https://firebase.google.com/docs/analytics/get-started?platform=android). If you encounter any problem during development, please refer to the  [Error Codes](https://firebase.google.com/docs/analytics/errors).
