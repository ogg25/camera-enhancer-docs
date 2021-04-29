---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references - Basic Settings
description: This is the documentation - Android API references - Basic Settings page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references, Basic Settings
needAutoGenerateSidebar: true
breadcrumbText: Android Basic Setting
---

# API Reference - Basic Setting

- [`getDeviceLevel`](#getdevicelevel)
- [`setAutoModeLevelParam`](#setautomodelevelparam)
- [`updateCameraSetting`](#updatecamerasetting)
- [`getVersion`](#getversion)
- [`enableFastMode`](#fast-mode)
- [`getEnabledFastModeStatus`](#fast-mode)
- [`getCameraDesireState`](#camera-state)
- [`setCameraDesireState`](#camera-state)
- [`getCameraCurrentState`](#camera-state)
- [`pauseCamera`](#pausecamera-and-resumecamera)
- [`resumeCamera`](#pausecamera-and-resumecamera)
- [`startScanning`](#stopscanning-and-startscanning)
- [`stopScanning`](#stopscanning-and-startscanning)
- [`addCameraListener`](#addcameralistener)
- [`removeCameraListener`](#addcameralistener)
- [`acquireListFrame`](#acquirelistframe)
- [`setTorchDesiredState`](#torch-state)
- [`getTorchDesiredState`](#torch-state)
- [`getTorchCurrentState`](#torch-state)
- [`addTorchListener`](#addtorchlistener)
- [`getCameraPosition`](#camera-position)
- [`switchCameraPosition`](#camera-position)
- [`getResolution`](#resolution-settings)
- [`setResolution`](#resolution-settings)
- [`getResolutionList`](#resolution-settings)

## getDeviceLevel

This API can help you make an evaluation on your mobile device. It will be helpful to automatically turn off DCE on high-level mobile devices.

```java
    mCamera.getDeviceLevel();
```

## setAutoModeLevelParam

Set auto mode level parameter - cpuMHz1, cpuMHz2, ramMB1, ramMB2. These are settings for device-level.

| CPU & RAM | If device CPUMHz > cpuMHz2 | If device CPUMHz1 < CPUMHz < cpuMHz2 | If device CPUMHz < CPUMHz1 |
|--|--|--|--|
| If device ramMB > ramMB2 | Device-level is high | Device-level is mid | Device-level is mid |
| If device ramMB1 < ramMB < ramMB2 | Device-level is mid | Device-level is mid | Device-level is mid |
| If device ramMB < ramMB1 | Device-level is mid | Device-level is mid | Device-level is low |

```java
    mCamera.setAutoModeLevelParam(int,int,int,int);
```

## updateCameraSetting

There are some detailed settings that can be updated from JSON.

To update from JSON string:

```java
    mCamera.updateCameraSetting("{"sensorvalue":3,"graydiffthreshold":30,"conversioncountthreshold":30,"sharpnessthreshold":0.2,"sharpnessthresholdlarge":0.4,"abssharpnessthreshold":200,"absgraythreshold":35,"claritythreshold":0.1}");
```

To update from JSON file:

```java
    mCamera.updateCameraSetting("Your file path here.");
```

JSON file template:

```json
    {
        //Absolute sharpness value, A threshold value for controlling filter
        "abssharpnessthreshold":200,
        //Sensor value, A threshold value for controlling filter
        "sensorvalue":3,        
        //A threshold value for gray scale analysis
        "graydiffthreshold":30,
        //A threshold for judging whether the device is shaking
        "sharpnessthreshold":0.2,
        //A threshold for judging whether the device is shaking violently
        "sharpnessthresholdlarge":0.4,
        //A threshold value for calculating sharpness
        "absgraythreshold":35,
        //A threshold value for controlling auto zoom
        "conversioncountthreshold":30,
        //A threshold value that controlling auto focus
        "claritythreshold":0.1
    }

```

## getVersion

Users can check the current DCE version by using this API.

```java
    mCamera.getVersion();
```

## Fast Mode

This API is designed for users to set up DCE fast mode. DCE fast mode will cut frames into small images that contain barcode areas to improve decode efficiency. It is recommended to be enabled when decoding a single barcode.

```java
    //To enable fast mode
    mCamera.enableFastMode(true);
    //To get the value(status) of fast mode
    boolean x = mCamera.getEnabledFastModeStatus();
```

## Camera State

Get current status (on/off) of the camera.

```java
    mCamera.getCameraCurrentState();
```

Get desired status (on/off) of the camera.

```java
    mCamera.getCameraDesireState();
```

Use `CameraState.CAMERA_STATE_ON` to set the camera on and use `CameraState.CAMERA_STATE_OFF` to set it off.

```java
    mCamera.setCameraDesireState(CameraState.CAMERA_STATE_OFF);
    mCamera.setCameraDesireState(CameraState.CAMERA_STATE_ON);
```

## pauseCamera and resumeCamera

Note: these APIs are created to pause & resume the camera. The camera module is still working when being paused. If you want to shut down the camera module, please use `stopScanning`.

```java
    mCamera.pauseCamera();
    mCamera.resumeCamera();
```

## stopScanning and startScanning

To control the stop & start of the camera module.

```java
    mCamera.startScanning();
    mCamera.stopScanning();
```

## addCameraListener

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

## acquireListFrame

This API is designed for users to acquire a single frame. When this API is activated, it will fetch the latest frame from the DCE frame list.

```java
    mCameraEnhancer.AcquireListFrame(true);
```

Remove Camera Listener

```java
    mCamera.removeCameraListener();
```

## Torch State

Get current torch state (on/off)

```java

    mCamera.getTorchCurrentState();
```

Get desired torch state (on/off)

```java
    mCamera.getTorchDesiredState();
```

Use `TorchState.TORCH_STATE_ON` to set the torch on and use `TorchState.TORCH_STATE_OFF` to set it off.

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

## Camera Position

DCE will use the back camera of your mobile device by default. You can use `getCameraPosition` to check which camera is activated and use `switchCameraPosition` to change the setting.
To get camera position:

```java
    mCamera.getCameraPosition();
```

To change settings, use `CameraPosition.CAMERA_POSITION_USER` to activate front camera and use `CameraPosition.CAMERA_POSITION_WORLD` to activate back camera

```java
    mCamera.switchCameraPosition(CameraPosition.CAMERA_POSITION_USER);
```

## Resolution Settings

These APIs are created for you to get or change camera resolution settings.

```java
    mCamera.getResolution();
```

Camera resolution parameters can be viewed in [`parameter-resolution`]({{site.reference}}#Resolution). If the resolution setting is not available in the device, the device will run the closest resolution to the set resolution.

```java
    mCamera.setResolution(Resolution.RESOLUTION_1080P);
```

Get all available resolutions that can be set to the current camera.

```java
    mCamera.getResolutionList();
```
