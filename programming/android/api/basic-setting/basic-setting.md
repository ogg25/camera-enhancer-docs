---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references - Basic Settings
description: This is the documentation - Android API references - Basic Settings page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references, Basic Settings
needAutoGenerateSidebar: true
breadcrumbText: Android Basic Setting
---

# API Reference - Basic Setting

- [`getDeviceLevel`](#getDeviceLevel)
- [`getApiVersion`](#getApiVersion)
- [`updateCameraSetting`](#updateCameraSetting)
- [`enableFastMode`](#FastMode)
- [`getEnableFastModeStatus`](#FastMode)
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

## getDeviceLevel

This API can help you make a evaluation on your mobile device. It will be helpful on automatically turn off DCE on high level mobile devices. 
```java
    mCamera.getDeviceLevel();
```

## getApiVersion

Get current DCE API version
```java
    mCamera.getApiVersion();
```

## updateCameraSetting

Some detailed settings that can be updated from JSON string or file.
To update from JSON string:
```java
    mCamera.updateCameraSetting("{"sensorvalue":3,"graydiffthreshold":30,"conversioncountthreshold":30,"sharpnessthreshold":0.2,"sharpnessthresholdlarge":0.4,"abssharpnessthreshold":200,"absgraythreshold":35,"claritythreshold":0.1}");
```
To update from JSON file:
```java
    mCamera.updateCameraSetting("Your file path here.");
```
JSON file template:
```Json
    {
        "sensorvalue":3,
        "graydiffthreshold":30,
        "conversioncountthreshold":30,
        "sharpnessthreshold":0.2,
        "sharpnessthresholdlarge":0.4,
        "abssharpnessthreshold":200,
        "absgraythreshold":35,
        "claritythreshold":0.1
    }

```

## FastMode
    
This API is designed for users to setup DCE fast mode. DCE fast mode will cut frames into small images that contains barcode area to improve decode efficiency. It is recommended to be enabled when decoding single barcode.
```java
    //To enable fast mode
    mCamera.enableFastMode(true);
    //To get the value(status) of fast mode
    boolean x = mCamera.getEnableFastModeStatus();
```

## getCameraCurrentState, getCameraDesireState and setCameraDesireState
    
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
    mCamera.setCameraDesireState(CameraState.CAMERA_STATE_OFF);
    mCamera.setCameraDesireState(CameraState.CAMERA_STATE_ON);
```
    
## pauseCamera and resumeCamera
Note: these APIs are created for pause & resume camera but camera module is still working when being paused. if you want to shut down camera module please use `stopScanning`.
```java
    mCamera.pauseCamera();
    mCamera.resumeCamera();
```
## stopScanning and startScanning
Contorl the stop & start of camera module.
```java
    mCamera.startScanning();
    mCamera.stopScanning();
```
## addCameraListener and removeCameraListener
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
## getTorchCurrentState, getTorchDesiredState and setTorchDesiredState

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
    mCamera.setTorchDesiredState(TorchState.TORCH_STATE_ON);
    mCamera.setTorchDesiredState(TorchState.TORCH_STATE_OFF);
```
## addTorchListener
```java
    mCamera.addTorchListener(new TorchListener() {
        @Override
        public void onTorchStateChanged(TorchState torchState) {
                
        }
    });
```

## getCameraPosition and switchCameraPosition
DCE will use back camera of your mobile device by default. You can use `getCameraPosition` to check which camera is activated and use `switchCameraPosition` to change the setting.
To get camera position:
```java
    mCamera.getCameraPosition();
```
To change settings, use `CameraPosition.CAMERA_POSITION_USER` to activate front camera and use `CameraPosition.CAMERA_POSITION_WORLD` to activate back camera
```java
    mCamera.switchCameraPosition(CameraPosition.CAMERA_POSITION_USER);
```
## getResolution and setResolution
These APIs are created for you to get or change camera resolution settings.
```java
    mCamera.getResolution();
```
Camera resolution parameters can be viewed in [`parameter-resolution`]({{site.reference}}#Resolution). If the resolution setting is not available in the device, the device will run the closest resolution to the setted resolution.
```java
    mCamera.setResolution(Resolution.RESOLUTION_1080P);
```