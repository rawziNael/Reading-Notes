# Android Fundamentals  
Kotlin, Java, and C++ are all languages that may be used to create Android apps. Your code, together with any data and resource files, is compiled into an APK, or
Android package, which is an archive file with an.apk suffix. APK files contain all of the contents of an Android software and are used to install the program on Android-powered
devices.  

Each Android program is contained within its own security sandbox, which is guarded by the Android security mechanisms listed below. Android is a multi-user Linux
operating system in which each program represents a separate user. Each process has its own virtual machine, and the system provides each app its own Linux user ID.
Every Linux process is dedicated to a single software.  


The Android system follows the concept of least privilege, which implies that each program has access to only the components it needs to accomplish its job.
Applications should be able to share data with other apps and use system functions. It's possible to set up two programs to share the same Linux user ID, allowing
them to access each other's data. An app might ask for access to data on the device, such as its location, camera, and Bluetooth connection.  

App components are the fundamental components of an Android app. There are four distinct kinds. Activities - a single screen with a user interface that serves as
the starting point for engaging with the user. The following are key interactions between the system and the app: keeping track of what the user is currently
interested in to ensure that the system keeps running the activity-hosting process; knowing that previously used processes contain things the user may return to;
assisting the app in handling its process being killed so that the user can return to activities with their previous state restored; and providing a way for a user
to return to activities with their previous state restored.  


Services is a general-purpose entry point for keeping a program running in the background for a variety of reasons, but it lacks a user interface. 
Bound services - run because another app has shown an interest in using the service, and this is essentially the service giving an API to another process. Started services - run
because another app has expressed an interest in using the service.  


Broadcast receivers are a component that allows the system to deliver events to the app outside of a regular user flow, allowing the app to respond to system-wide
broadcast announcements. They don't have a user interface, but you can create a status bar notification to notify the user when a broadcast event occurs. Content 
providers handle a common set of app data that you may store on the file system, in a SQLite database, on the web, or anywhere else your app can access persistent
storage.  

Components that are activated - an asynchronous communication called an intent activates three of the four components. Individual components are bound to one other
at runtime by intents, which are defined with an Intent object, which provides a message to activate either a single component or a certain type of component.
Content providers are enabled by a request from a ContentResolver, which handles all direct transactions with the content provider so that the component doing the
transactions doesn't have to, and instead uses methods on the ContentResolver object.  

The Android system must first know that an app component exists by reading the app's manifest file, AndroidManifest.xml. Manifest specifies the app's components.
Elements that are used to declare components. It indicates any permissions that the program wants from the user. Based on the APIs the app utilizes, it specifies the
minimum API Level required by the app. It lists the hardware and software features that the app uses or requires. It specifies which API libraries the program must
link against. By adding an element as a child of the component's declaration element, you may specify an intent filter for your component.    

Resources for the application An Android app requires resources other than source code, such as pictures, audio files, and anything related to the app's visual
appearance. The SDK build tools assign a unique numeric ID to each resource you include, which you may use to refer to it in your app code or from other XML resources.
The ability to provide alternative resources for different device settings is one of the most significant features of supplying resources independent from your source
code. Android allows a variety of qualifiers for your alternative resources. For your alternative resources, Android provides a variety of qualifications. 
Qualifier - a brief string that you include in the name of your resource directories to specify the device configuration for which they should be utilized.
