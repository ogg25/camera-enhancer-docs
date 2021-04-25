---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references - Basic Setting
description: This is the documentation - Objective-C & Swift API references - Basic Setting page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references, Basic Setting
needAutoGenerateSidebar: true
breadcrumbText: iOS Basic Setting
---

# iOS API Reference - Basic Setting

- [`updateCameraSettingFromJson`](#updateCameraSettingFromJson)
- [`updateCameraSettingFromFile`](#updateCameraSettingFromFile)
- [`enableFastMode`](#enableFastMode)
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

## updateCameraSettingFromJson

Some detailed settings that can be updated from JSON string or file.
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

## getCameraCurrentState, getCameraDesiredState and setCameraDesiredState
    
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
    
Use `This content will be changed` to set camera on and use `This content will be changed` to set it off.

Objective-C
```objectivec
    [dce setCameraDesiredState:DCEnhancerStateOn];
```
Use `This content will be changed` to set camera on and use `This content will be changed` to set it off.
Swift
```Swift
    dce.setCameraDesiredState(CameraState.off)
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

## addCameraListener and removeCameraListener

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

## getTorchCurrentState, getTorchDesiredState and setTorchDesiredState

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

Use `<!--This content will be changed-->` to set torch on and use `<!--This content will be changed-->` to set it off.

Objective-C
```objectivec
    [dce setTorchDesiredState:DCETorchStateOn];
```

Swift
```Swift
    dce.setTorchDesiredState(TorchState.on)
```

## addTorchListener and removeTorchListener

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

## getCameraPosition and switchCameraPosition

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

## getResolution and setResolution

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
