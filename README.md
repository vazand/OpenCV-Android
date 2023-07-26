# OpenCV-Android
Using opencv in android project I'm using Android studio Flamingo version and OpenCV-android-sdk-4.8.0

1. download opencv-android-sdk latest version from https://opencv.org/releases/ and extract the zip
2. copy the `OpenCV-android-sdk/sdk` directory and paste it in your project's root folder 
3. open an empty or existing android studio project and open folders in project view, make sure that our sdk folder is here.
4. Add the follwing line in the gradle.properties `android.defaults.buildfeatures.buildconfig=true`
5. open sdk/java/AndroidManifest.xml and delete `package="org.opencv"`
   
6.1. open sdk/build.gradle and add `namespace 'org.opencv'` inside `android{}`

6.2. open sdk/build.gradle and add this inside end of `android{}`   
``buildFeatures{
            aidl true
        }``
        
6.3. open the sdk/build.gradle, change the `targetSdkVersion` and `compileSdkVersion` are latest and same. //I've used 33 

6.4 if you're using kotin then add kotlinOptions in `android{}` add the following

  ``kotlinOptions{
        jvmTarget="1.8" // here I'm using JVM 1.8
    }``
    
7. open settings.gradle and add `include ':sdk'` in the end of the file.
8. sync the project
9. Goto Files>Project Structure> Dependencies 
	select app then select `+` from declared dependencies and select `Module dependency`
	Here you can see the `sdk` folder in step.1 click it and make sure `implementation` in step.2 give ok.	 
10. make project and run. :) 
