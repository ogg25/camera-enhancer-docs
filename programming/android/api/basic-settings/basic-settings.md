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
- [`setErrorCode`](#setErrorCode)
- [`getCameraDesireState`](#getCameraCurrentState-getCameraDesireState-&-setCameraDesireState)
- [`setCameraDesireState`](#getCameraCurrentState-getCameraDesireState-&-setCameraDesireState)
- [`getCameraCurrentState`](#getCameraCurrentState-getCameraDesireState-&-setCameraDesireState)
- [`pauseCamera`](#pauseCamera-&-resumeCamera)
- [`resumeCamera`](#pauseCamera-&-resumeCamera)
- [`startScanning`](#stopScanning-&-startScanning)
- [`stopScanning`](#stopScanning-&-startScanning)
- [`addCameraListener`](#addCameraListener-&-removeCameraListener)
- [`removeCameraListener`](#addCameraListener-&-removeCameraListener)
- [`setTorchDesiredState`](#getTorchCurrentState-getTorchDesiredState-&-setTorchDesiredState)
- [`getTorchDesiredState`](#getTorchCurrentState-getTorchDesiredState-&-setTorchDesiredState)
- [`getTorchCurrentState`](#getTorchCurrentState-getTorchDesiredState-&-setTorchDesiredState)
- [`addTorchListener`](#addTorchListener)
- [`getCameraPosition`](#getCameraPosition-&-switchCameraPosition)
- [`switchCameraPosition`](#getCameraPosition-&-switchCameraPosition)
- [`getResolution`](#getResolution-&-setResolution)
- [`setResolution`](#getResolution-&-setResolution)

### setErrorCode
```java
    mCamera.setErrorCode(true);
```
### getCameraCurrentState, getCameraDesireState & setCameraDesireState
    
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
    
### pauseCamera & resumeCamera
Note: these APIs are created for pause & resume camera but camera module is still working when being paused. if you want to shut down camera module please use `stopScanning`.
```java
    try {
        mCamera.pauseCamera();
        //mCamera.resumeCamera();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```
### stopScanning & startScanning
Contorl the stop & start of camera module.
```java
    try {
        mCamera.startScanning();
        //mCamera.stopScanning();
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```
### addCameraListener & removeCameraListener
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
### getTorchCurrentState, getTorchDesiredState & setTorchDesiredState

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

### getCameraPosition & switchCameraPosition
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
### getResolution & setResolution
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