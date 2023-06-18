# Defensive Drone Simulator(DDS)

## What is this?

 The defensive drone simulator application plays a significant role in our proposed system. It computes the future GPS coordinates of the malicious drone based on its past trajectory. The computed GPS data is then translated back into control data using the DJI Android API, allowing the defensive drone to autonomously fly to the calculated GPS point.
 
<br>
<br>

### What are functions?

1. Display TSPI data.
2. Calculate the predicted path.
3. Autonomous drone driving.
4. Save the Log file(.csv).

<br>
<br>

### Test Environment

- Device: galaxy tab a7 lite (Android 11)
- laptop: Macbook Air 2(M2)


<br>
<br>

### 🖥️ Application User Interface

The widget settings rate is aligned with the tablet rate. If you want to see a screen that fits the ratio, please use the tablet to run it.

- Register Page

![Untitled](Defensive%20Drone%20Simulator(DDS)%205a7e27c26aa94994b7b15f5542248995/Untitled.png)

- Main Page

![Untitled](Defensive%20Drone%20Simulator(DDS)%205a7e27c26aa94994b7b15f5542248995/Untitled%201.png)


<br>
<br>


### 📁 Directory

```html
.
├── main
│   ├── AndroidManifest.xml
│   ├── java
│   │   └── com
│   │       └── dji
│   │           └── sdk
│   │               └── venture
│   │                   ├── BackgroundCallback.java
│   │                   ├── Interface
│   │                   │   └── IQueue.java
│   │                   ├── MApplication.java
│   │                   ├── MainActivity.java
│   │                   ├── RegisterActivity.java
│   │                   ├── TSPI.java
│   │                   └── Utils
│   │                       ├── CircularQueueUtil.java
│   │                       └── GPSUtil.java
│   └── res
│       ├── drawable
│       ├── layout
│       │   ├── activity_connection.xml
│       │   └── activity_main.xml
│       ├── mipmap
│       ├── values
│       │   ├── colors.xml
│       │   ├── strings.xml
│       │   └── themes.xml
│       ├── values-night
│           └── themes.xml
```

<br>
<br>

### ⚠️ Precautions

- You need to connect your DJI drone to go to the main page of the app. You cannot go to the main page of the app without the drone.
- When using the application for the first time, Wi-Fi must be connected because the DJI SDK must be installed.
- You must restart the application after compiling it to run the application.

---

<br>
<br>


## 🗒️ Environment settings

### Requirements

- Android Studio 3.2+
- Android System 4.1+
- DJI Android SDK 4.16.4

### Required API key

- DJI Developer Key
- Firebase API Key
- Google Maps API Key

### Integration

Declare dependency via 

**Gradle:app**

```java
dependencies {
    implementation 'androidx.appcompat:appcompat:1.6.1'
    implementation 'androidx.constraintlayout:constraintlayout:2.1.4'
    implementation 'com.google.android.material:material:1.4.0-alpha02'
    testImplementation 'junit:junit:4.13.2'
    androidTestImplementation 'androidx.test.ext:junit:1.1.5'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.5.1'
    implementation 'com.google.firebase:firebase-firestore:24.1.1'
    implementation ('com.google.firebase:firebase-bom:32.0.0')
    implementation 'com.google.android.gms:play-services-maps:18.1.0'
    implementation 'com.google.android.gms:play-services-location:20.0.0'
    implementation 'com.google.android.material:material:1.0.0'
    implementation 'com.squareup:otto:1.3.8'
    implementation('com.dji:dji-sdk:4.16.4', {
        exclude module: 'fly-safe-database'
        exclude module: 'library-anti-distortion'
    })
    compileOnly 'com.dji:dji-sdk-provided:4.16.4'
}
```

**Gradle: Project**

```java
dependencies {
        classpath 'com.google.gms:google-services:4.3.15'
    }
```

For further detail on how to integrate the DJI Android SDK into your Android Studio project, please check the [Integrate SDK into Application](http://developer.dji.com/mobile-sdk/documentation/application-development-workflow/workflow-integrate.html#import-maven-dependency) tutorial.

### Android Gradle Plugin Version + Gradle Version

- Android Gradle Plugin Version : 7.4.0
- Gradle Version : 7.5

![Untitled](Defensive%20Drone%20Simulator(DDS)%205a7e27c26aa94994b7b15f5542248995/Untitled%202.png)

### Modules

- Recommend 33(API : Android 13.0) or lower

![Untitled](Defensive%20Drone%20Simulator(DDS)%205a7e27c26aa94994b7b15f5542248995/Untitled%203.png)

### JDK version

- Recommend JDK 17 or JDK 8

![Untitled](Defensive%20Drone%20Simulator(DDS)%205a7e27c26aa94994b7b15f5542248995/Untitled%204.png)

### Modules

| Dependency | Configuration |
| --- | --- |
| androidx.appcompat:appcompat:1.6.1 | implementation |
| androidx.constraintlayout:constraintlayout:2.1.4 | implementation |
| com.dji:dji-sdk-provided:4.16.4 | compileOnly |
| com.dji:dji-sdk:4.16.4 | implementation |
| androidx.test.espresso:espresso-core:3.5.1 | androidTestImplementation |
| com.google.firebase:firebase-bom:32.0.0 | implementation |
| com.google.firebase:firebase-firestore:24.1.1 | implementation |
| androidx.test.ext:junit:1.1.5 | androidTestImplementation |
| junit:junit:4.13.2 | testImplementation |
| com.google.android.material:material:1.0.0 | implementation |
| com.google.android.material:material:1.4.0-alpha02 | implementation |
| com.squareup:otto:1.3.8 | implementation |
| com.google.android.gms:play-services-location:20.0.0 | implementation |
| com.google.android.gms:play-services-maps:18.1.0 | implementation |

---

<br>
<br>

## 📚 Reference

The following reference were used to develop the application.

- https://github.com/dji-sdk/Mobile-SDK-Android
- [Integrate Google API tutorial](https://developers.google.com/maps/documentation/android-sdk/overview)
- [Add Firebase Android project](https://firebase.google.com/docs/android/setup)
- [DJI Developer Document](https://developer.dji.com/document/544659e8-9dab-4ad8-9414-a31e1c9b89b1)
- [https://github.com/DJI-Mobile-SDK-Tutorials](https://github.com/DJI-Mobile-SDK-Tutorials)

---

<br>
<br>

## 📞 Contact

- Uk Jang
    - E-Mail: mag0225@naver.com
    
    [Uk-jake - Overview](https://github.com/Uk-jake)
