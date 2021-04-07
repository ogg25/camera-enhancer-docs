---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references
description: This is the documentation - Objective-C & Swift API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references
needAutoGenerateSidebar: true
breadcrumbText: Objective-C & Swift
---

# Dynamsoft Camera Enhancer - Objective-C & Swift API references

## Basic Settings

### Initialization

- [`intiLicenseFromLTS`]()
- [`initWithView`]()
- [`enableBeepSound`]()
- [`updateCameraSettingFromJson`]()
- [`updateCameraSettingFromFile`]()

### Fastmode

- [`setFastmode`]()

### Camera setting
- [`getCameraDesiredState`](#getCameraCurrentState-getCameraDesiredState-and-setCameraDesiredState)
- [`setCameraDesiredState`](#getCameraCurrentState-getCameraDesiredState-and-setCameraDesiredState)
- [`getCameraCurrentState`](#getCameraCurrentState-getCameraDesiredState-and-setCameraDesiredState)
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

### updateCameraSettingFromJson

```objectivec
    [dce updateCameraSettingFromJson:@"json string"];
```
```Swift
    dce.updateCameraSetting(fromJson: "Your json string");
```

### updateCameraSettingFromFile

```objectivec
    [dce updateCameraSettingFromFile:@"your json file path"];
```
```Swift
    dce.updateCameraSetting(fromFile: "Your file path");
```

### enableBeepSound

```objectivec
    [dce enableBeepSound];
```
```Swift
    dce.enableBeepSound = true;
```

### setFastmode

Turn on fast mode

```objectivec
    [dce setFastMode:true];
```
```Swift
    dce.setFastMode(true);
```

### getCameraCurrentState, getCameraDesiredState and setCameraDesiredState
    
Get camera current status (on/off). 

```objectivec
    [dce getCameraCurrentState];
```
```Swift
    dce.getCameraCurrentState();
```
    
Get camera desired status (on/off).

```objectivec
    [dce getCameraDesiredState];
```
```Swift
    dce.getCameraDesiredState();
```
    
Use `DCEnhancerStateOn` to set camera on and use `DCEnhancerStateOff` to set it off.

```objectivec
    [dce setCameraDesiredState:DCEnhancerStateOn];
```
```Swift
    dce.setCameraDesiredState(CameraState.off);
```
    
### pauseCamera and resumeCamera

Note: these APIs are created for pause & resume camera but camera module is still working when being paused. if you want to shut down camera module please use `stopScanning`.

```objectivec
    [dce pauseCamera];
    [dce resumeCamera];
```
```Swift
    dce.pauseCamera();
    dce.resumeCamera();
```

### stopScanning and startScanning

Contorl the stop & start of camera module.

```objectivec
    [dce stopScanning];
    [dce startScanning];
```
```Swift
    dce.startScanning();
    dce.stopScanning();
```

### addCameraListener and removeCameraListener

Add Camera Listener

```objectivec
    [dce addCameraListener:self];
```
```Swift
    dce.addCameraListener(self);
```

Remove Camera Listener

```objectivec
    [dce removeCameraListener];
```
```Swift
    dce.removeCameraListener();
```

### getTorchCurrentState, getTorchDesiredState and setTorchDesiredState

Get current torch state (on/off)

```objectivec
    [dce getTorchCurrentState];
```
```Swift
    dce.getTorchCurrentState();
```

Get desired torch state (on/off)

```objectivec
    [dce getTorchDesiredState];
```
```Swift
    dce.getTorchDesiredState();
```

Use `DCETorchStateOn` to set torch on and use `DCETorchStateOff` to set it off.

```objectivec
    [dce setTorchDesiredState:DCETorchStateOn];
```
```Swift
    dce.setTorchDesiredState(TorchState.on);
```

### addTorchListener and removeTorchListener

```objectivec
    [dce addTorchListener:self];
    [dce removeTorchListener];
```
```Swift
    dce.addTorchListener(self);
    dce.removeCameraListener();
```

### getCameraPosition and switchCameraPosition

DCE will use back camera of your mobile device by default. You can use `getCameraPosition` to check which camera is activated currently.

```objectivec
    [dce getCameraPosition];
```
```Swift
    dce.getCameraPosition();
```

To change to another camera:

```objectivec
    [dce switchCameraPosition];
```
```Swift
    dce.switchCameraPosition();
```

### getResolution and setResolution

These APIs are created for you to get or change camera resolution settings. 

```objectivec
    [dce getResolution];
    [dce setResolution:Resolution1080P];
```
```Swift
    dce.getResolution();
    dce.setResolution(Resolution.Quality1080P);
```