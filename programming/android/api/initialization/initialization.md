---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references
description: This is the documentation - Android API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references
needAutoGenerateSidebar: true
breadcrumbText: Java
---

# Dynamsoft Camera Enhancer - Android API references

## Initialization and other basic settings

- [`CameraEnhancer`](#CameraEnhancer-&-addCameraView)
- [`addCameraView`](#CameraEnhancer-&-addCameraView)
- [`initLicenseFromLTS`](#initLicenseFromLTS)
- [`getDeviceLevel`](#getDeviceLevel)
- [`setApiVersion`](#getApiVersion-&-setApiVersion)
- [`getApiVersion`](#getApiVersion-&-setApiVersion)
- [`setEnableBeepSound`](#setEnableBeepSound)

### CameraEnhancer & addCameraView

These 2 APIs are created for the initialization of DCE. For more initialization detail please view [Android user guide]().
    
Code Snippet
```java
public class MainActivity extends AppCompatActivity {
    CameraEnhancer mCamera;
    CameraView cameraView;
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        mCamera = new CameraEnhancer(MainActivity.this);
        cameraView = findViewById(R.id.cameraView);
        mCamera.addCameraView(cameraView);
    }
}  
```

### initLicenseFromLTS

Initialize your license from License Tracking Server (LTS).
```java
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

### getDeviceLevel

Get your device level. It will be helpful on automatically turn off DCE on high level mobile devices. 
```java
    mCamera.getDeviceLevel();
```

### getApiVersion & setApiVersion

Get and set API version
```java
    mCamera.getApiVersion();
    mCamera.setApiVersion(int);
```

### setEnableBeepSound

Turn on beep sound. Currently only available for DBR users.
```java
    mCamera.setEnableBeepSound(true);
```
