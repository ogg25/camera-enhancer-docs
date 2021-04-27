---
layout: default-layout
title: Dynamsoft Camera Enhancer - Guide on Java(Android)
description: This is the documentation - Guide on Java(Android) page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Guide on Java(Android)
needAutoGenerateSidebar: true
breadcrumbText: Android Guide draft
---

# Guide on Java(Android)

## System Requirements

- Operating system:
    - Supported OS: Android 5 or higher (Android 7 or higher recommended)
    - Supported ABI: arm64-v8a/armeabi-v7a/x86/x86_6

## Installation

1. <a href="https://download.dynamsoft.com/dce/dce-android-1.0.zip?ver=latest" target="_blank">Download Dynamsoft Camera Enhancer</a> from Dynamsoft website to get `dce-android-{version-number}.zip`. Unzip the package to find `DynamsoftCameraEnhancerAndroid.aar`. 

2. Create a new Android project in Android Studio.

2. Put the `.aar` file under the dictionary `/app/libs` in your project. 

3. Add following code into `build.gradle(Module: app)`.
    ```Java
    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

4. Also in `build.gradle(Module: app)` add reference in dependencies:
    ```java
        implementation(name: 'DynamsoftCameraEnhancerAndroid', ext: 'aar')
    ```

5. Sync the project with gradle and after that `DynamsoftCameraEnhancerAndroid.aar` is added to your project.

## Get Started

### Create a Camera Module

In this section you will be guide on using Dynamsoft Camera Enhancer to create a simple camera app with video frame filter function.

1. Create a CameraView section in activity_main.xml.

    ```XML
        <com.dynamsoft.dce.CameraView
            android:id="@+id/cameraView"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            tools:layout_editor_absoluteX="25dp"
            tools:layout_editor_absoluteY="0dp" />
    ```

2. Set up for your camera in the `cameraView` section. Please add following code in your activity for camera. The following code is an example of setting camera view in `MainActivity`.

    ```java
    import com.dynamsoft.dce.CameraEnhancer;
    import com.dynamsoft.dce.CameraEnhancerException;
    import com.dynamsoft.dce.CameraState;
    import com.dynamsoft.dce.CameraView;
    import com.dynamsoft.dce.DMLTSConnectionParameters;
    import com.dynamsoft.dce.CameraLTSLicenseVerificationListener;
    //You can change the MainActivity to your prefer Activity 
    public class MainActivity extends AppCompatActivity {
        CameraEnhancer mCamera;
        CameraView cameraView;
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            //Remember to use your personal settings in this section     
            setContentView(R.layout.activity_main);
            cameraView = findViewById(R.id.cameraView);
            mCamera = new CameraEnhancer(MainActivity.this);
            mCamera.addCameraView(cameraView);
            //Initialize your license
            com.dynamsoft.dce.DMLTSConnectionParameters info = new com.dynamsoft.dce.DMLTSConnectionParameters();
            // The organization id 200001 here will grant you a public trial license good for 7 days.
            // After that, you can send an email to trial@dynamsoft.com
            // (make sure to include the keyword privateTrial in the email title)
            // to obtain a 30-day free private trial license which will also come in the form of an organization id.
            info.organizationID = "200001";
            mCamera.initLicenseFromLTS(info,new CameraLTSLicenseVerificationListener() {
                @Override
                public void LTSLicenseVerificationCallback(boolean isSuccess, Exception error) {
                    if(!isSuccess){
                        error.printStackTrace();
                    }
                }
            });
            //Turn on camera
            mCamera.setCameraDesiredState(CameraState.CAMERA_STATE_ON);
            //Start scanning
            mCamera.startScanning();
        }
    }
    ```

3. Run the project and now your camera module is running. If you have any question on the program, you can view `samples` we provided in the package you download to have better understandings. Also, you can get help from our online customer service.

### Create a Simple Video Stream Decoder

This section is the guide for users to create a video stream decoder with the help of DCE. In this section, Dynamsoft Barcode Reader will support on decode works.

1. Create a camera module

2. Add DCE filter settings and camera listener
    ```Java
    import com.dynamsoft.dce.CameraEnhancer;
    import com.dynamsoft.dce.CameraEnhancerException;
    import com.dynamsoft.dce.CameraState;
    import com.dynamsoft.dce.CameraView;
    import com.dynamsoft.dce.DMLTSConnectionParameters;
    import com.dynamsoft.dce.CameraLTSLicenseVerificationListener;
    //You can change the MainActivity to your prefer Activity 
    public class MainActivity extends AppCompatActivity {
        CameraEnhancer mCamera;
        CameraView cameraView;
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            //Remember to use your personal settings in this section     
            setContentView(R.layout.activity_main);
            cameraView = findViewById(R.id.cameraView);
            mCamera = new CameraEnhancer(MainActivity.this);
            mCamera.addCameraView(cameraView);
            //Initialize your license
            com.dynamsoft.dce.DMLTSConnectionParameters info = new com.dynamsoft.dce.DMLTSConnectionParameters();
            // The organization id 200001 here will grant you a public trial license good for 7 days.
            // After that, you can send an email to trial@dynamsoft.com
            // (make sure to include the keyword privateTrial in the email title)
            // to obtain a 30-day free private trial license which will also come in the form of an organization id.
            info.organizationID = "200001";
            mCamera.initLicenseFromLTS(info,new CameraLTSLicenseVerificationListener() {
                @Override
                public void LTSLicenseVerificationCallback(boolean isSuccess, Exception error) {
                    if(!isSuccess){
                        error.printStackTrace();
                    }
                }
            });
            //Turn on camera
            mCamera.setCameraDesiredState(CameraState.CAMERA_STATE_ON);
            //Start scanning
            mCamera.startScanning();
            //From Camera listener, users can fetch frames for decoding 
            mCamera.addCameraListener(new CameraListener() {
            @Override
            public void onPreviewOriginalFrame(Frame frame) {
                //Get original frames here
            }
            @Override
            public void onPreviewFilterFrame(Frame frame) {
                //Get filtered frames here
            }
            @Override
            public void onPreviewFastFrame(Frame frame) {
                //Get fast mode frames here
            }
        });
        }
    }
    ```

3. Auto filter & focus setting
    ```Java
    ```

## Add DCE to your Dynamsoft Barcode Reader (DBR) project

For developers who are using Dynamsoft Barcode reader, there are new APIs in DBR 8.2.1 mobile edition to quick deploy camera enhancer in barcode reader project. For more information please read more in [DBR documentation - camera enhancer deployment]({{site.barcode-deploy-android}}) section. 