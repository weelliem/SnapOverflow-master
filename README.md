## SnapOverflow
We are living in a world of connectivity with social media applications like Facebook and Instagram
allowing more and more people to connect with each other in unimaginable ways at just a touch of
their figure tips. This android application will allow students/friends to connect and communicate with each other via geo-location. 
The application will allow students/friends to tag a geolocation with an image / message of a question that they need
assistance with and other students/friends within the area can comment / reply to the image /
message with a solution to the question. Overall the aim is to create a giant discussion board that
allow students to help and interact with each other in real time

## Table of Content 
* [Prerequisites](#prerequisites)
* [Building-APK](#building-apk)
* [Features](#features)
* [Component-Overview](#component-overview)
* [APIs](#apis)
* [Bugs](#bugs)
* [Credits](#credits)


## Prerequisites
It is recommended to have the latest version of android studio **4.0.1** and to have updated your android gradle-plugin **4.0.1** to allow for gradle **6.1.1.** and SDK Build Tools **29.0.2 or higher**.

## Building-APK
In android studio **Build > Build Bundle(s) / APK > Build APK(s)**

## Features
* **Authentication Feature** 
this feature will use Firebase authentication specifically the email and
password authentication process. Since Firebase is already used as the database system for the
application it makes the storage of user information simpler. Firebase also has an email confirmation
system which will also be used to increase the security of the system

* **Google Maps Geo-Tagging** 
This feature contains google maps API which uses the phones onboard GPS and other sensors to track
and location the current location of the user which is a real-time tracker that updates with googles
Fused Location Provider client. This client intelligently uses multiple sensors to get accurate data 
The map fragment also requires several permissions to be granted since the location of the user is
private information it requires multiple one time checks to allow for the application to function this is
manually coded

* **Camera** 
This feature is the camera which is created with the old API instead of the new camera2 API this reason
to use the old feature is because there is no need to incorporate the new features of camera2 because
the depreciated camera API have all the feature required to simply take a photo and send it to firebase.
This section of the code was required to encode data since the photo is taken and encoded as bytes
which means it needed to decode into a bitmap and then saved at an internal memory location to
transfer between activities. 
After decoding and sending the bitmap it must be encoded back into bytes because firebase storage
only accepts data in that form which means the reencoding of the image is done and any other
information is also saved eventually is packaged as a hash map to firebase

* **Discussion Board** 
This is the Discussion board implementation of a recycle view with uses
Firebase Real-time Database which means that the recycle view is in
constant sync with firebase, the structure of the feature follows the same
recycle view structure
The layout manager is the intermediary between the adapter and the
recycle view it basically makes calls to the adapter on behalf of the recycle
view.
The adapter basically does all the heavy lifting by communicating with the
dataset to populate the recycle view however in this case where firebase is involved the adapter
extracts data which is directly grabbed from firebases real-time database and presents it on the recycle
view which is visible to the user

* **Firebase Adapter** 
This is the same as the adapter that was explained above however it’s a bit different. The firebase
recycler adaptor monitors changes to firebase and does real time changes to the recycle view. The
best point about the firebase adaptor is the automatic updating and querying that is handled by
firebase which leads to less coding for you 

## Component-Overview
**Model View View-Model**

The model view view-Model (MVVM) architectural pattern is somewhat used within this application
to facilitate all the activates and classes. The MVVM uses three different components the View, the
View-Model and Model.
The model is responsible for the data and state of the application it is not tied to the view it is
basically the data access layer of the architecture.
The view is the same as the views within the MVVM is the same as any other architecture MVP or
MVC it is the structure, layout and appearance. However, there is one different the view binds
observable variables and actions to the model views.
The view model the most unique feature is a mediator between the model and view it
communicates with the view with bindings and updates the model with commands. 

## APIs
* **Google Firebase Database**
This is the real-time cloud hosed database for Firebase it uses and scalable NoSQL which stores data
as JSON.

* **Firebase Authentication**
Firebase Authentication API provides backend services to support either your own custom user
authentication or using premade authentication tokens from Facebook, google or Twitter.
Firebase Recycler View Adaptor / Firebase UI Database
Firebase UI is a simple library that binds data from the real-time database to your applications. It
allows for easy population of recycle view by using firebase adaptors.

* **Firebase Storage**
This is basically being a cloud storage API which allows you easily to store and access data.

* **Google Play Services Maps**
This is the API that allows the use of google map on your application

* **Google Maps Utils**
This is the is a library that allows the use of marker clustering, heat maps and icon generating.

* **Google Play Services Location**
This uses google play services to facilitate location awareness and other geolocation features

* **Fused Location Provider Client**
This API uses both WIFI, GPS and google play services sensors to efficiently gather the location of the
device this is a solution to the battery issues the conventional GPS methods provide.

* **Picasso**
Picasso is a powerful image downloading and cache API that handles images within your application.

* **Camera 1**
This is a depreciated camera API however for this application it functions as required. It supports
camera features on the device allowing you to capture video and images.

* **Fragments**
The fragment library allows the for a specific behaviour of a portion of user interface. It allows for
more flexible UI designs.

* **Android Data Binding**
The data binding library allows the binding of UI components in your activities to methods or
variables in your application.

* **Recycle/Card View**
This basically allows the use of recycle and card views within your application.

## Bugs
* 12/08/2020 - due to adroid studio upgrading their android versions the swipe navagation is alot more sensitive therefore make sure to use the edge of the screen while slow swiping

## Credits 
Thanks to Ryan Heist the UTS subject co-ordinator for insignt in the development process

© William Hong 2020



 
