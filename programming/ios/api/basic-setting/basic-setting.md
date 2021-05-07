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

## updateCameraSettingFromJson

There are Some detailed settings that can be updated from JSON string or file. [View JSON data template and explanation](#updatecamerasettingfromfile)
To update from JSON string:

Objective-C:

```objectivec
    [dce updateCameraSettingFromJson:@"json string"];
```

Swift:

```swift
    dce.updateCameraSetting(fromJson: "Your json string")
```

## updateCameraSettingFromFile

There are some detailed settings that can be updated from JSON string or file.
To update from JSON file:

Objective-C:

```objectivec
    [dce updateCameraSettingFromFile:@"your json file path"];
```

Swift:

```swift
    dce.updateCameraSettingFromFile(fromFile: "Your file path")
```

This is the template for `updateCameraSettingFromJson` and `updateCameraSettingFromFile`:

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

Users can check the current DCE version by using this API.

Objective-C:

```objectivec
    [dce getVersion];
```

Swift:

```swift
    dce.getVersion()
```

## enableFastMode

This API is designed for users to set up DCE fast mode. DCE fast mode will cut frames into small images that contain barcode areas to improve decode efficiency. It is recommended to be enabled when decoding a single barcode.

Objective-C:

```objectivec
    [dce enableFastMode:true];
    //To check the status of DCE fast mode
    [dce getEnableFastMode];
```

Swift:

```swift
    dce.enableFastMode = true
```

## Camera State

Use `getCameraCurrentState`, `getCameraDesiredState` and `setCameraDesiredState` to make settings on camera state.
Get the current status (on/off) of the camera.

Objective-C:

```objectivec
    [dce getCameraCurrentState];
```

Swift:

```swift
    dce.getCameraCurrentState()
```

Get the desired status (on/off)of the camera.

Objective-C:

```objectivec
    [dce getCameraDesiredState];
```

Swift:

```swift
    dce.getCameraDesiredState()
```

Use `CAMERA_STATE_ON` to set the camera on and use `CAMERA_STATE_OFF` to set it off.

Objective-C:

```objectivec
    [dce setCameraDesiredState:CAMERA_STATE_ON];
```

Swift:

```swift
    dce.setCameraDesiredState(CAMERA_STATE_ON)
```

## pauseCamera and resumeCamera

Note: these APIs are created to pause & resume the camera. The camera module is still working when being paused. if you want to shut down the camera module please use `stopScanning`.

Objective-C:

```objectivec
    [dce pauseCamera];
    [dce resumeCamera];
```

Swift:

```swift
    dce.pauseCamera()
    dce.resumeCamera()
```

## stopScanning and startScanning

To control the stop & start of the camera module.

Objective-C:

```objectivec
    [dce startScanning];
    [dce stopScanning];
```

Swift:

```swift
    dce.startScanning()
    dce.stopScanning()
```

## addCameraListener

Add Camera Listener

Objective-C:

```objectivec
    [dce addCameraListener:self];
```

Swift:

```swift
    dce.addCameraListener(self)
```

Remove Camera Listener

Objective-C:

```objectivec
    [dce removeCameraListener];
```

Swift:

```swift
    dce.removeCameraListener()
```

## acquireListFrame

This API is designed for users to acquire a single frame. When this API is activated, it will fetch the latest frame from the DCE frame list.

Objective-C:

```objectivec
    FramePackage *fg = [self.camera AcquireListFrame];
```

Swift:

```swift
    let fg = self.dce.acquireListFrame() 
```

## Torch State

Use `getTorchCurrentState`, `getTorchDesiredState` and `setTorchDesiredState` to make settings on torch state
Get current torch state (on/off)

Objective-C:

```objectivec
    [dce getTorchCurrentState];
```

Swift:

```swift
    dce.getTorchCurrentState()
```

Get desired torch state (on/off)

Objective-C:

```objectivec
    [dce getTorchDesiredState];
```

Swift:

```swift
    dce.getTorchDesiredState()
```

Use `TorchState.TORCH_STATE_ON` to set the torch on and use `TorchState.TORCH_STATE_OFF` to set it off.

Objective-C:

```objectivec
    [dce setTorchDesiredState:TorchState.on];
```

Swift:

```swift
    dce.setTorchDesiredState(TorchState.on)
```

## addTorchListener

Objective-C:

```objectivec
    [dce addTorchListener:self];
    [dce removeTorchListener];
```

Swift:

```swift
    dce.addTorchListener(self)
    dce.removeCameraListener()
```

## Camera Position

DCE will use the back camera of your mobile device by default. You can use `getCameraPosition` to check which camera is activated currently.

Objective-C:

```objectivec
    [dce getCameraPosition];
```

Swift:

```swift
    dce.getCameraPosition()
```

To change to another camera:

Objective-C:

```objectivec
    [dce switchCameraPosition];
```

Swift:

```swift
    dce.switchCameraPosition()
```

## Resolution Settings

These APIs are created for you to get or change camera resolution settings.

Objective-C:

```objectivec
    [dce getResolution];
    [dce setResolution:Resolution1080P];
```

Swift:

```swift
    dce.getResolution()
    dce.setResolution(Resolution.Quality1080P)
```

`getResolutionList` enables users to check all available resolutions that can be set to the current camera.

Objective-C:

```objectivec
    [dce getResolutionList];
```

Swift:

```swift
    dce.getResolutionList()
```
