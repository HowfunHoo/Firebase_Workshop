# Firebase Console Instructions

### Creat Firebase Account & Add Project

1. Create an account in Firebase. URL -> https://firebase.google.com/
2. Select "Add Project" from Firebase Console.
3. Enter project name (same as App name) and country on the "Add a project" window.

### Add Firebase to app

#### Generate google-services.json file

1. From the Firebase Dashboard, click 'Add Firebase to your Android app'
2. Enter package name (app package name) in the "Enter App Details" section.
3. Other optional fields can be added as per requirment and click 'Register App'.
4. Download and save the generated 'google-services.json' file.
5. Move the json file to the app module root directory in Android Studio.

#### Add Google-services plugin

(Following to be done on Android Studio)

1. Add the below line of code to <dependencies> section in "<project>/build.gradle" file
  
        classpath 'com.google.gms:google-services:3.2.0'
    
2. Add the below code to <dependencies> section in '<project>/<app-module>/build.gradle' file,
  
        compile 'com.google.firebase:firebase-core:11.8.0'
    
   To the bottom of the file add the following line of code,
   
        apply plugin: 'com.google.gms.google-services'

3. Click 'Sync Now' in the Android Studio IDE to synchronize the app with Firebase google-services plugin.

### Add Firebase Authentication Service to app

1. Select 'Authentication' under "Develop" section in the Firebase Dashboard screen.
2. Go to 'SIGN-IN METHOD' tab.
3. Enable 'Email/Password' authentication. (Select all that apply to your app)

### Methods in Firebase Authenticate SDK

1. Create FirebaseAuth instance under the 'onCreate()' method in the activity java file.

          FirebaseAuth auth = FirebaseAuth.getInstance();
          
2. Invoke createUserWithEmailAndPassword() method using FirebaseAuth instance, created in previous step, to add an user to firebase.

          auth.createUserWithEmailAndPassword(email, password)

          
