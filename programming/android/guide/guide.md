---
layout: default-layout
title: Dynamsoft Camera Enhancer - Guide on Java(Android)
description: This is the documentation - Guide on Java(Android) page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Guide on Java(Android)
needAutoGenerateSidebar: true
breadcrumbText: Java(Android)
---

# Dynamsoft Camera Enhancer - Guide on Java(Android)

## Quick access

- [Installation](#Installation)
- [Get start with DCE](#Get-Start)
- [Add DCE to your project](#Add-DCE-to-your-project)

## System Requirements

- Operating system:
    - Supported OS: Android 5 or higher (Android 7 or higher recommended)
    - Supported ABI: armeabi-v7a, arm64-v8a

## Installation

1. [Download Dynamsoft Camera Enhancer]() from Dynamsoft website to get `dce-android-{version-number}.zip`. Unzip the package to find `DynamsoftCameraEnhancer-release.aar`. 

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
        implementation(name: 'DynamsoftCameraEnhancer-release', ext: 'aar')
    ```

5. Sync the project with gradle and after that `DynamsoftCameraEnhancer-release.aar` is added to your project.

## License initialization

If you have already got a full key license from `License Tracking Server`, you can use the following code to set it up in your project:

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

If you don't have a full key license:

- 7 days trial license is available for new devices that have never setup Dynamsoft Camera Enhancer.
- To extend your trial license, please send "Private trial" to trial@dynamsoft.com to get 30 days private trial key.

Or you can

- [Learn more about full key license]()

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

2. Set up for your camera in the `cameraView` section. Please add following code in your activity for camera. The following code is an example of setting camera view in `MainActivity`

    ```java
    import com.dynamsoft.dce.CameraEnhancer;
    import com.dynamsoft.dce.CameraEnhancerException;
    import com.dynamsoft.dce.CameraState;
    import com.dynamsoft.dce.CameraView;
    //You can change the MainActivity to your prefer Activity 
    public class MainActivity extends AppCompatActivity {
        //Here will add License intialization
        CameraEnhancer mCamera;
        CameraView cameraView;
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            //******************************************************
            //Remember to use your personal settings in this section
            //******************************************************            
            setContentView(R.layout.activity_main);
            cameraView = findViewById(R.id.cameraView);
            mCamera = new CameraEnhancer(MainActivity.this);
            //******************************************************
            //******************************************************
            mCamera.addCameraView(cameraView);
            //Turn on camera
            try {
                mCamera.setCameraDesiredState(CameraState.CAMERA_STATE_ON);
            } catch (CameraEnhancerException e) {
                e.printStackTrace();
            }
            //Start scanning
            try {
                mCamera.startScanning();
            } catch (CameraEnhancerException e) {
                e.printStackTrace();
            }
        }
    }
    ```

3. Remember to add use permission to your project.

    ```XML
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.CAMERA" />
    ```

4. Run the project and now your camera module is running. If you have any question on the program, you can view `samples` we provided in the package you download to have better understandings. Also, you can get help from our online customer service.

### Quick settings for DCE

In this section, you can find some useful APIs that helps you on initialize DCE efficiently.

1. Setting Template
    The following template is strongly recommended to be applicated in your first attempt on DCE. This template will be friendly to the majority of mobile devices. By using and optimizing on this template, you will quickly be familiar with DCE. 
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
                mCamera.setCameraDesiredState(CameraState.CAMERA_STATE_ON);
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
            //Filter, zoom & Focus settings
            mCamera.setErrorCode(true);        
            mCamera.setSensorControl(true);
            mCamera.setAutoZoom(true);
            mCamera.setForceAutoFocus(true);
            mCamera.setFastMode(true);
        }
    ```

2. Fast mode setting

    DCE fast mode is specially designed for accelerating on single barcode decoding. This mode will reduce the time consumption on single barcode decoding by 50%. Fast mode is strongly recommended to be enabled on single barcode decoding. To turn on Fast mode, you can use `setFastMode` to make the setting:
    
    ```Java
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        requestWindowFeature(Window.FEATURE_ACTION_BAR);
        setContentView(R.layout.activity_main);
        cameraView = findViewById(R.id.cameraView);
        mCamera = new CameraEnhancer(MainActivity.this);
        mCamera.addCameraView(cameraView);
        try {
            mCamera.setCameraDesiredState(CameraState.CAMERA_STATE_ON);
            } catch (CameraEnhancerException e) {
                e.printStackTrace();
            }
        try {
                mCamera.startScanning();
            } catch (CameraEnhancerException e) {
                e.printStackTrace();
            }

        //***************Turn on Fast mode**********************
        mCamera.setFastMode(true);
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

## Add DCE to your project

If you have a completed project and you want to add Dynamsoft Camera Enhancer into your app, the following guide might help you on quick installation. For Dynamsoft Barcode reader (DBR) developers, we provide following APIs in our 8.3+ version to easily set up DCE in your DBR project.

|API names|Description|
|---------|-----------|
| `setDCE` |  |
| `startDCE` |  |
| `endDCE` |  |
| `setDCEresultCallback` |  |
