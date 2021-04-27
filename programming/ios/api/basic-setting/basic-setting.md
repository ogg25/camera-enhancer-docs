---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references - Basic Setting
description: This is the documentation - Objective-C & Swift API references - Basic Setting page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references, Basic Setting
needAutoGenerateSidebar: true
breadcrumbText: iOS Basic Setting
---

# iOS API Reference - Basic Setting

- [`updateCameraSettingFromJson`](#updatecamerasettingfromjson)
- [`updateCameraSettingFromFile`](#updatecamerasettingfromfile)
- [`getVersion`](#getversion)
- [`enableFastMode`](#enablefastmode)
- [`getCameraDesiredState`](#camera-state)
- [`setCameraDesiredState`](#camera-state)
- [`getCameraCurrentState`](#camera-state)
- [`pauseCamera`](#pausecamera-and-resumecamera)
- [`resumeCamera`](#pausecamera-and-resumecamera)
- [`startScanning`](#stopscanning-and-startscanning)
- [`stopScanning`](#stopscanning-and-startscanning)
- [`addCameraListener`](#addcameralistener)
- [`removeCameraListener`](#addcameralistener)
- [`setTorchDesiredState`](#torch-state)
- [`getTorchDesiredState`](#torch-state)
- [`getTorchCurrentState`](#torch-state)
- [`addTorchListener`](#addtorchlistener)
- [`getCameraPosition`](#camera-position)
- [`switchCameraPosition`](#camera-position)
- [`getResolution`](#resolution-settings)
- [`setResolution`](#resolution-settings)
- [`getResolutionList`](#resolution-settings)

## updateCameraSettingFromJson

Some detailed settings that can be updated from JSON string or file. [View JSON data template and explanation](#updatecamerasettingfromfile)
To update from JSON string:

Objective-C
```objectivec
    [dce updateCameraSettingFromJson:@"json string"];
```

Swift
```Swift
    dce.updateCameraSetting(fromJson: "Your json string")
```

## updateCameraSettingFromFile

Some detailed settings that can be updated from JSON string or file.
To update from JSON file:

Objective-C
```objectivec
    [dce updateCameraSettingFromFile:@"your json file path"];
```

Swift
```Swift
    dce.updateCameraSettingFromFile(fromFile: "Your file path")
```

This is the template for `updateCameraSettingFromJson` and `updateCameraSettingFromFile`

```Json
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

User can check the current DCE version by using this API.

Objective-C
```objectivec
    [dce getVersion];
```

Swift
```Swift
    dce.getVersion()
```

## enableFastMode

This API is designed for users to setup DCE fast mode. DCE fast mode will cut frames into small images that contains barcode area to improve decode efficiency. It is recommended to be enabled when decoding single barcode.

Objective-C
```objectivec
    [dce enableFastMode:true];
    //To check the status of DCE fast mode
    [dce getEnableFastMode];
```

Swift
```Swift
    dce.enableFastMode = true
```

## Camera State

Use `getCameraCurrentState`, `getCameraDesiredState` and `setCameraDesiredState` to make settings on camera state.
Get camera current status (on/off). 

Objective-C
```objectivec
    [dce getCameraCurrentState];
```

Swift
```Swift
    dce.getCameraCurrentState()
```
    
Get camera desired status (on/off).

Objective-C
```objectivec
    [dce getCameraDesiredState];
```

Swift
```Swift
    dce.getCameraDesiredState()
```
    
Use `CAMERA_STATE_ON` to set camera on and use `CAMERA_STATE_OFF` to set it off.

Objective-C
```objectivec
    [dce setCameraDesiredState:CAMERA_STATE_ON];
```
Use `CAMERA_STATE_ON` to set camera on and use `CAMERA_STATE_OFF` to set it off.

Swift
```Swift
    dce.setCameraDesiredState(CAMERA_STATE_ON)
```
    
## pauseCamera and resumeCamera

Note: these APIs are created for pause & resume camera but camera module is still working when being paused. if you want to shut down camera module please use `stopScanning`.

Objective-C
```objectivec
    [dce pauseCamera];
    [dce resumeCamera];
```

Swift
```Swift
    dce.pauseCamera()
    dce.resumeCamera()
```

## stopScanning and startScanning

Contorl the stop & start of camera module.

Objective-C
```objectivec
    [dce startScanning];
    [dce stopScanning];
```

Swift
```Swift
    dce.startScanning()
    dce.stopScanning()
```

## addCameraListener

Add Camera Listener

Objective-C
```objectivec
    [dce addCameraListener:self];
```

Swift
```Swift
    dce.addCameraListener(self)
```

Remove Camera Listener

Objective-C
```objectivec
    [dce removeCameraListener];
```

Swift
```Swift
    dce.removeCameraListener()
```

## Torch State

Use `getTorchCurrentState`, `getTorchDesiredState` and `setTorchDesiredState` to make settings on torch state
Get current torch state (on/off)

Objective-C
```objectivec
    [dce getTorchCurrentState];
```

Swift
```Swift
    dce.getTorchCurrentState()
```

Get desired torch state (on/off)

Objective-C
```objectivec
    [dce getTorchDesiredState];
```

Swift
```Swift
    dce.getTorchDesiredState()
```

Use `TorchState.TORCH_STATE_ON` to set torch on and use `TorchState.TORCH_STATE_OFF` to set it off.

Objective-C
```objectivec
    [dce setTorchDesiredState:TorchState.on];
```

Swift
```Swift
    dce.setTorchDesiredState(TorchState.on)
```

## addTorchListener

Objective-C
```objectivec
    [dce addTorchListener:self];
    [dce removeTorchListener];
```

Swift
```Swift
    dce.addTorchListener(self)
    dce.removeCameraListener()
```

## Camera Position

DCE will use back camera of your mobile device by default. You can use `getCameraPosition` to check which camera is activated currently.

Objective-C
```objectivec
    [dce getCameraPosition];
```

Swift
```Swift
    dce.getCameraPosition()
```

To change to another camera:

Objective-C
```objectivec
    [dce switchCameraPosition];
```

Swift
```Swift
    dce.switchCameraPosition()
```

## Resolution Settings

These APIs are created for you to get or change camera resolution settings. 

Objective-C
```objectivec
    [dce getResolution];
    [dce setResolution:Resolution1080P];
```

Swift
```Swift
    dce.getResolution()
    dce.setResolution(Resolution.Quality1080P)
```

`getResolutionList` enable user to check all available resolutions that can be setted to the current camera.

Objective-C
```objectivec
    [dce getResolutionList];
```

Swift
```Swift
    dce.getResolutionList()
```
