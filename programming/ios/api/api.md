---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references
description: This is the documentation - Objective-C & Swift API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references
needAutoGenerateSidebar: true
breadcrumbText: iOS API Reference
---

# Objective-C & Swift (iOS) API references

- [Initialization](#initializationlicenseandotherbasicsettings)
- [Basic Camera Settings](#basiccamerasettings)
- [Focus Settings](#focussettings)
- [Zoom Settings](#zoomsettings)
- [Filter Setting](#filtersettings)

## Initialization, License and other basic settings

| Method | Description |
|-----------------|---------------|
| [`updateCameraSettingFromJson`]({{site.ios-basic-setting}}basic-setting.html#updatecamerasettingfromjson) | Update camera filter and focus settings from Json |
| [`updateCameraSettingFromFile`]({{site.ios-basic-setting}}basic-setting.html#updatecamerasettingfromfile) | Update camera filter and focus settings from file |

## Fast mode

| Method | Description |
|-----------------|---------------|
| [`enableFastMode`]({{site.ios-basic-setting}}basic-setting.html#setfastmode) | Set the value true/false to turn on/off DCE fast mode |

## Camera Setting

### Basic Camera Settings

| Method | Description |
|-----------------|---------------|
| [`setCameraDesiredState`]({{site.ios-basic-setting}}basic-setting.html#getcameracurrentstate-getcameradesirestate-and-setcameradesirestate) | Set Camera on/off |
| [`getCameraDesiredState`]({{site.ios-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera desired state |
| [`getCameraCurrentState`]({{site.ios-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera current state |
| [`pauseCamera`]({{site.ios-basic-setting}}basic-setting.html#pauseCamera-and-resumeCamera) | Pause Camera |
| [`resumeCamera`]({{site.ios-basic-setting}}basic-setting.html#pauseCamera-and-resumeCamera) | Resume Camera |
| [`startScanning`]({{site.ios-basic-setting}}basic-setting.html#stopScanning-and-startScanning) | Start scanning |
| [`stopScanning`]({{site.ios-basic-setting}}basic-setting.html#stopScanning-and-startScanning) | Stop scanning |
| [`addCameraListener`]({{site.ios-basic-setting}}basic-setting.html#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) |
| [`removeCameraListener`]({{site.ios-basic-setting}}basic-setting.html#addCameraListener-and-removeCameraListener) | Remove camera listener |
| [`setTorchDesiredState`]({{site.ios-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Set torch state |
| [`getTorchDesiredState`]({{site.ios-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch desired state |
| [`getTorchCurrentState`]({{site.ios-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch current state |
| [`addTorchListener`]({{site.ios-basic-setting}}basic-setting.html#addTorchListener-and-removeTorchListener) | Add torch listener |
| [`removeTorchListener`]({{site.ios-basic-setting}}basic-setting.html#addTorchListener-and-removeTorchListener) | Remove Torch Listener |
| [`getCameraPosition`]({{site.ios-basic-setting}}basic-setting.html#getCameraPosition-and-switchCameraPosition) | Get current camera position |
| [`switchCameraPosition`]({{site.ios-basic-setting}}basic-setting.html#getCameraPosition-and-switchCameraPosition) | Switch camera position front/back |
| [`setResolution`]({{site.ios-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Set resolution |
| [`getResolution`]({{site.ios-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Get current resolution setting |
| [`getResolutionList`](basic-setting/basic-setting.md#getResolution-and-setResolution) | Get all available resolutions |

## Focus Settings

- Focus parameters related APIs:

| Method | Description |
|-----------------|---------------|
| [`setAutoFocusPosition`]({{site.ios-zoom-setting}}zoom-focus.html#setAutoFocusPosition) | Set auto focus position (Change the default auto focus position). |
| [`setManualFocusPosition`]({{site.ios-zoom-setting}}zoom-focus.html#setManualFocusPosition) | Set manual focus position (This focus position only effect once for each time the API is called). |
| [`setFocalLength`]({{site.ios-zoom-setting}}zoom-focus.html#setFocalLength) | Set focal length between 0 to 10 to enable fixed focal length mode. In fixed focal length mode, all focus parameters can't be changed until this mode is quit. To quit fixed focal length mode, please set focal length equals to -1. |

- Basic focus settings:

| Method | Description |
|-----------------|---------------|
| [`enableDCEAutoFocus`]({{site.ios-zoom-setting}}zoom-focus.html#enableDCEAutoFocus) | Set true/false to turn on/off DCE auto focus. |
| [`enableDefaultAutoFocus`]({{site.ios-zoom-setting}}zoom-focus.html#enableDefaultAutoFocus) | Set true/false to turn on/off default auto focus. |

- Advanced focus settings: 

| Method | Description |
|-----------------|---------------|
| [`enableRegularAutoFocus`]({{site.ios-zoom-setting}}zoom-focus.html#enableRegularAutoFocus) | If this is true, camera will auto focus for every 3 seconds. This focus mode will start automatically if DCE auto focus is enabled. Users can manually quit this focus mode when DCE auto focus is activated. |
| [`setRegularAutoFocusParam`] | Set parameters for regular auto focus mode. Focus interval and terminate time are available for setting in this API |
| [`enableAutoFocusOnSharpnessChange`]({{site.ios-zoom-setting}}zoom-focus.html#enableAutoFocusOnSharpnessChange) | If this is enabled, camera will auto focus when clarity change is detected. This focus mode will start automatically if DCE auto focus is enabled. Users can manually quit this focus mode when DCE auto focus is activated. |

## Zoom Settings
| Method | Description |
|-----------------|---------------|
| [`enableAutoZoom`]({{site.ios-zoom-setting}}zoom-focus.html#enableAutoZoom) | Set enableAutoZoom value true to enable auto zoom mode. |
| [`setZoomFactor`]({{site.ios-zoom-setting}}zoom-focus.html#setZoomFactor) | Set zoom factor |

## Filter Settings

| Method | Description |
|-----------------|---------------|
| [`enableSensorControl`]({{site.ios-filter-setting}}filter.html#setSensorControl) | Set true/false to turn on/off DCE sensor control. |
| [`enableFrameFilter`]({{site.ios-filter-setting}}filter.html#setUseFrameFilter) | Set true/false to turn on/off DCE frame filter. |
| [`setMaxFrameRate`]({{site.ios-filter-setting}}filter.html#setMaxFrameRate) | Set max frame rate |
| [`setFrameListLength`]({{site.ios-filter-setting}}filter.html#setFrameListLength) | Set how many frames will be stored in list. |