---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references
description: This is the documentation - Android API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references
needAutoGenerateSidebar: true
breadcrumbText: Java
---

# Dynamsoft Camera Enhancer - Android API references

## Camera settings - Basic Setting

- [`getDeviceLevel`](#getDeviceLevel)
- [`setApiVersion`](#getApiVersion-and-setApiVersion)
- [`getApiVersion`](#getApiVersion-and-setApiVersion)
- [`updateCameraSetting`](#updateCameraSettingFromJson-and-updateCameraSetting)
- [`enableFastMode`](#enableFastMode)
- [`setErrorCode`](#setErrorCode)
- [`getCameraDesireState`](#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState)
- [`setCameraDesireState`](#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState)
- [`getCameraCurrentState`](#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState)
- [`pauseCamera`](#pauseCamera-and-resumeCamera)
- [`resumeCamera`](#pauseCamera-and-resumeCamera)
- [`startScanning`](#stopScanning-and-startScanning)
- [`stopScanning`](#stopScanning-and-startScanning)
- [`addCameraListener`](#addCameraListener-and-removeCameraListener)
- [`removeCameraListener`](#addCameraListener-and-removeCameraListener)
- [`setTorchDesiredState`](#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState)
- [`getTorchDesiredState`](#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState)
- [`getTorchCurrentState`](#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState)
- [`addTorchListener`](#addTorchListener)
- [`getCameraPosition`](#getCameraPosition-and-switchCameraPosition)
- [`switchCameraPosition`](#getCameraPosition-and-switchCameraPosition)
- [`getResolution`](#getResolution-and-setResolution)
- [`setResolution`](#getResolution-and-setResolution)

### getDeviceLevel

Get your device level. It will be helpful on automatically turn off DCE on high level mobile devices. 
```java
    mCamera.getDeviceLevel();
```

### getApiVersion and setApiVersion

Get and set API version
```java
    mCamera.getApiVersion();
    mCamera.setApiVersion(int);
```

### updateCameraSettingFromJson and updateCameraSettingFromFile

```Json
    
```

### enableFastMode
    
Turn on(off) fast mode. It is recommended to turned on when decoding single barcode.
```java
    mCamera.enableFastMode(true);
```

### setErrorCode
```java
    mCamera.setErrorCode(true);
```

### getCameraCurrentState, getCameraDesireState and setCameraDesireState
    
Get camera current status (on/off). 
```java
    mCamera.getCameraCurrentState();
```
    
Get camera desired status (on/off).
```java
    mCamera.getCameraDesireState();
```
    
Use `CameraState.CAMERA_STATE_ON` to set camera on and use `CameraState.CAMERA_STATE_OFF` to set it off.
```java
    try {
        mCamera.setCameraDesireState(CameraState.CAMERA_STATE_OFF);
        //mCamera.setCameraDesireState(CameraState.CAMERA_STATE_ON);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```
    
### pauseCamera and resumeCamera
Note: these APIs are created for pause & resume camera but camera module is still working when being paused. if you want to shut down camera module please use `stopScanning`.
```java
    try {
        mCamera.pauseCamera();
        //mCamera.resumeCamera();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```
### stopScanning and startScanning
Contorl the stop & start of camera module.
```java
    try {
        mCamera.startScanning();
        //mCamera.stopScanning();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```
### addCameraListener and removeCameraListener
Add Camera Listener
```java
    mCamera.addCameraListener(new CameraListener() {
        @Override
        public void onPreviewOriginalFrame(Frame frame) {

        }
        @Override
        public void onPreviewFilterFrame(Frame frame) {

        }

        @Override
        public void onPreviewFastFrame(Frame frame) {

        }
    });
```
Remove Camera Listener
```java
    mCamera.removeCameraListener();
```
### getTorchCurrentState, getTorchDesiredState and setTorchDesiredState

Get current torch state (on/off)
```java
    mCamera.getTorchCurrentState();
```

Get desired torch state (on/off)
```java
    mCamera.getTorchDesiredState();
```

Use `TorchState.TORCH_STATE_ON` to set torch on and use `TorchState.TORCH_STATE_OFF` to set it off.
```java
    try {
        mCamera.setTorchDesiredState(TorchState.TORCH_STATE_ON);
        //mCamera.setTorchDesiredState(TorchState.TORCH_STATE_OFF);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```
### addTorchListener
```java
    mCamera.addTorchListener(new TorchListener() {
        @Override
        public void onTorchStateChanged(TorchState torchState) {
                
        }
    });
```

### getCameraPosition and switchCameraPosition
DCE will use back camera of your mobile device by default. You can use `getCameraPosition` to check which camera is activated and use `switchCameraPosition` to change the setting.
To get camera position:
```java
    mCamera.getCameraPosition();
```
To change settings, use `CameraPosition.CAMERA_POSITION_USER` to activate front camera and use `CameraPosition.CAMERA_POSITION_WORLD` to activate back camera
```java
    try {
        mCamera.switchCameraPosition(CameraPosition.CAMERA_POSITION_USER);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```
### getResolution and setResolution
These APIs are created for you to get or change camera resolution settings. 
```java
    mCamera.getResolution();
```
For more details on camera resolution parameters, please view [parameter - resolution]()
```java
    try {
        mCamera.setResolution(Resolution.RESOLUTION_1080P);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```