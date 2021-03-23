---
layout: default-layout
title: Dynamsoft Camera Enhancer - Guide on Android
description: This is the documentation - Guide on Android page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Guide on Android
needAutoGenerateSidebar: true
breadcrumbText: Java
---

# Dynamsoft Camera Enhancer - Guide on Android

## Quick access

- [Installation]()
- [Get start with DCE]()
- [Set DCE in you DBR project]()

## System Requirements

- Operating system:
    - Supported OS: Android 5 or higher (Android 7 or higher recommended)
    - Supported ABI: armeabi-v7a, arm64-v8a

## Installation

1. [Download 30 days free trial]() to get `dce-android-{version-number}.zip`. Unzip the package to find `DynamsoftCameraEnhancer-release.aar`. 

2. Put the `.aar` file under the dictionary `/app/libs` in your project. 

3. Add following code into `build.gradle(Module: app)`
    ```Java
    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

4. Also in `build.gradle(Module: app)` add reference in dependencies:
    ```java
        implementation(name: 'DynamsoftBarcodeReaderAndroid', ext: 'aar')
    ```

5. Sync the project with gradle and after that `DynamsoftCameraEnhancer-release.aar` is added to your project.

## License initialization

To initialize your license, you have to connect to the License Tracking Server for online verification. There is the code for you to initialize your license. 
```Java
    CameraLTSConnectionParameters info = new CameraLTSConnectionParameters();
    info.sessionPassword = "******";
    info.handshakeCode ="******";
    mCamera.initLicenseFromLTS(info, new CameraLTSLicenseVerificationListener() {
        @Override
        public void LTSLicenseVerificationCallback(boolean b, Exception e) {
            if(!b && e != null){
                e.printStackTrace();
            }
        }
    });
```

## Get Start

### Create a Camera module

In this section you will be guide on using Dynamsoft Camera Enhancer to create a simple camera app with video frame filter function.

1. Create a CameraView section in the XML file that you want to run a camera.

    ```XML
        <com.dynamsoft.dce.CameraView
            android:id="@+id/cameraView"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            tools:layout_editor_absoluteX="25dp"
            tools:layout_editor_absoluteY="0dp" />
    ```

2. Set up for your camera in the cameraView section. Please add following code in your activity for camera.

    ```java
            //Add two parameters in your Activity
            CameraEnhancer mCamera;
            CameraView cameraView;
    ```
    ``` java
            //To initialize your cameraView, please add following codes into your onCreate
            //Please fill in the id you created for your camera view, in our sample, it is "cameraView"
            cameraView = findViewById(R.id.cameraView);
            //Initialize your camera
            mCamera = new CameraEnhancer(MainActivity.this);
            mCamera.addCameraView(cameraView);
            //Set camera state on
            try {
                mCamera.setCameraDesireState(CameraState.CAMERA_STATE_ON);
            } catch (CameraEnhancerException e) {
                e.printStackTrace();
            }
    ```

3. Remember to add use permission to your project.

    ```XML
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.CAMERA" />
    ```

4. Run the project and now your camera module is running. If you have any question on the program, you can [download samples]() to have better understandings.

### Quick settings for DCE

In this section, you can find some useful APIs that helps you on initialize DCE efficiently.

1. Setting Template
    The following template of DCE setting is strongly recommended to be applicated in your first attempt on DCE. This setting will be friendly to the majority of mobile devices. 
    ```java
        CameraEnhancer mCamera;
        CameraView cameraView;
        protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        requestWindowFeature(Window.FEATURE_ACTION_BAR);
        setContentView(R.layout.activity_main);
        cameraView = findViewById(R.id.cameraView);
        mCamera = new CameraEnhancer(MainActivity.this);
        mCamera.addCameraView(cameraView);
        try {
            mCamera.setCameraDesireState(CameraState.CAMERA_STATE_ON);
        } catch (CameraEnhancerException e) {
            e.printStackTrace();
        }
        //License Initialization
        CameraLTSConnectionParameters info = new CameraLTSConnectionParameters();
        info.sessionPassword = "******";
        info.handshakeCode ="******";
        mCamera.initLicenseFromLTS(info, new CameraLTSLicenseVerificationListener() {
            @Override
            public void LTSLicenseVerificationCallback(boolean b, Exception e) {
                if(!b && e != null){
                    e.printStackTrace();
                }
            }
        });
        //Start camera scanning
        try {
            mCamera.startScanning();
        } catch (CameraEnhancerException e) {
            e.printStackTrace();
        }
        //FIlter, zoom & Focus settings
        mCamera.setErrorCode(true);        
        mCamera.setSensorControl(true);
        mCamera.setAutoZoom(true);
        mCamera.setForceAutoFocus(true);
        mCamera.setUseFrameFilter(true);
        mCamera.setFastMode(true);
    }
    ```

2. Camera setting

    DCE will use back camera by default. You can use `switchCameraPosition` to change this setting. `CameraPosition.CAMERA_POSITION_USER` stands for front camera and `CameraPosition.CAMERA_POSITION_WORLD` stands for back camera. There is a sample for how you can write a function to switch your camera position. 
    
    ```Java
        public void switch_camera_position(View view){
        if(mCamera.getCameraPosition() == CameraPosition.CAMERA_POSITION_WORLD){
            try {
                mCamera.switchCameraPosition(CameraPosition.CAMERA_POSITION_USER);
            } catch (CameraEnhancerException e) {
                e.printStackTrace();
            }
        }
        else {
            try {
                mCamera.switchCameraPosition(CameraPosition.CAMERA_POSITION_WORLD);
            } catch (CameraEnhancerException e) {
                e.printStackTrace();
            }
        }
    }
    ```

3. Auto filter & focus setting

    Since some mobile devices have enough powerful camera, we don't need to force DCE to run on these devices. `getDeviceLevel` is designed for making more flexible settings to applicate proper algorithm on devices with different level. The follow code is a sample on how we can turn off frame filter and auto focus on high level devices. For parameters on device level, please view parameters for [`HardwareUtil`]().

    ```Java
        boolean ifNeedFilter = true;
        boolean ifNeedAutoFocus = true;
        int deviceLevel = mCamera.getDeviceLevel();
        if (deviceLevel == HardwareUtil.DEVICE_LEVEL_HIGH)
        {
            ifNeedFilter = false;
            ifNeedAutoFocus = false;
        }
        if(deviceLevel == HardwareUtil.DEVICE_LEVEL_MID)
        {
            ifNeedAutoFocus = false;
        }
        mCamera.setForceAutoFocus(ifNeedAutoFocus);
        mCamera.setUseFrameFilter(ifNeedFilter);
    ```




### Add DCE to your app

If you have a completed project and you want to add Dynamsoft Camera Enhancer into your app, the following guide might help you on quick installation. For Dynamsoft Barcode reader (DBR) developers, we provide following APIs in our 8.3+ version to easily set up DCE in your DBR project.

|API names|Description|
|---------|-----------|
|`setDCE`||
|`startDCE`||
|`endDCE`||
|`setDCEresultCallback`||
