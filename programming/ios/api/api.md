---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references
description: This is the documentation - Objective-C & Swift API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references
needAutoGenerateSidebar: true
breadcrumbText: iOS API Reference
---

# Objective-C & Swift (iOS) API references

- [Initialization](#initialization)
- [Fast Mode](#fast-mode)
- [Basic Camera Settings](#basic-camera-settings)
- [Focus Settings](#focus-settings)
- [Zoom Settings](#zoom-settings)
- [Filter Setting](#filter-settings)

## Initialization

| Method | Description |
|-----------------|---------------|
| [`updateCameraSettingFromJson`]({{site.ios-basic-setting}}basic-setting.html#updatecamerasettingfromjson) | Update camera filter and focus settings from Json |
| [`updateCameraSettingFromFile`]({{site.ios-basic-setting}}basic-setting.html#updatecamerasettingfromfile) | Update camera filter and focus settings from file |
| [`getVersion`]({{site.ios-basic-setting}}basic-setting.html#getversion) | Check current DCE version |

## Fast mode

| Method | Description |
|-----------------|---------------|
| [`enableFastMode`]({{site.ios-basic-setting}}basic-setting.html#enablefastmode) | Set the value true/false to turn on/off DCE fast mode |

## Camera Setting

### Basic Camera Settings

| Method | Description |
|-----------------|---------------|
| [`setCameraDesiredState`]({{site.ios-basic-setting}}basic-setting.html#camera-state) | Set Camera on/off |
| [`getCameraDesiredState`]({{site.ios-basic-setting}}basic-setting.html#camera-state) | Get camera desired state |
| [`getCameraCurrentState`]({{site.ios-basic-setting}}basic-setting.html#camera-state) | Get camera current state |
| [`pauseCamera`]({{site.ios-basic-setting}}basic-setting.html#pausecamera-and-resumecamera) | Pause Camera |
| [`resumeCamera`]({{site.ios-basic-setting}}basic-setting.html#pausecamera-and-resumecamera) | Resume Camera |
| [`startScanning`]({{site.ios-basic-setting}}basic-setting.html#stopscanning-and-startscanning) | Start scanning |
| [`stopScanning`]({{site.ios-basic-setting}}basic-setting.html#stopscanning-and-startscanning) | Stop scanning |
| [`addCameraListener`]({{site.ios-basic-setting}}basic-setting.html#addcameralistener) | Add camera listener (on preview original, filtered or fast frames) |
| [`removeCameraListener`]({{site.ios-basic-setting}}basic-setting.html#addcameralistener) | Remove camera listener |
| [`setTorchDesiredState`]({{site.ios-basic-setting}}basic-setting.html#torch-state) | Set torch state |
| [`getTorchDesiredState`]({{site.ios-basic-setting}}basic-setting.html#torch-state) | Get torch desired state |
| [`getTorchCurrentState`]({{site.ios-basic-setting}}basic-setting.html#torch-state) | Get torch current state |
| [`addTorchListener`]({{site.ios-basic-setting}}basic-setting.html#addtorchlistener) | Add torch listener |
| [`removeTorchListener`]({{site.ios-basic-setting}}basic-setting.html#addtorchlistener) | Remove Torch Listener |
| [`getCameraPosition`]({{site.ios-basic-setting}}basic-setting.html#camera-position) | Get current camera position |
| [`switchCameraPosition`]({{site.ios-basic-setting}}basic-setting.html#camera-position) | Switch camera position front/back |
| [`setResolution`]({{site.ios-basic-setting}}basic-setting.html#resolution-settings) | Set resolution |
| [`getResolution`]({{site.ios-basic-setting}}basic-setting.html#resolution-settings) | Get current resolution setting |
| [`getResolutionList`](basic-setting/basic-setting.md#resolution-settings) | Get all available resolutions |

## Focus Settings

- Focus parameters related APIs:

| Method | Description |
|-----------------|---------------|
| [`setAutoFocusPosition`]({{site.ios-zoom-setting}}zoom-focus.html#setautofocusposition) | Set auto focus position (Change the default auto focus position). |
| [`setManualFocusPosition`]({{site.ios-zoom-setting}}zoom-focus.html#setmanualfocusposition) | Set manual focus position (This focus position only effect once for each time the API is called). |
| [`setFocalLength`]({{site.ios-zoom-setting}}zoom-focus.html#setfocallength) | Set focal length between 0 to 10 to enable fixed focal length mode. In fixed focal length mode, all focus parameters can't be changed until this mode is quit. To quit fixed focal length mode, please set focal length equals to -1. |

- Basic focus settings:

| Method | Description |
|-----------------|---------------|
| [`enableDefaultAutoFocus`]({{site.ios-zoom-setting}}zoom-focus.html#enabledefaultautofocus) | Set true/false to turn on/off default auto focus. |

- Advanced focus settings:

| Method | Description |
|-----------------|---------------|
| [`enableRegularAutoFocus`]({{site.ios-zoom-setting}}zoom-focus.html#enableregularautofocus) | If this is true, camera will auto focus for every 3 seconds. |
| [`enableAutoFocusOnSharpnessChange`]({{site.ios-zoom-setting}}zoom-focus.html#enableautofocusonsharpnesschange) | If this is enabled, camera will auto focus when clarity change is detected. |

## Zoom Settings

| Method | Description |
|-----------------|---------------|
| [`enableAutoZoom`]({{site.ios-zoom-setting}}zoom-focus.html#enableautozoom) | Set enableAutoZoom value true to enable auto zoom mode. |
| [`setZoomFactor`]({{site.ios-zoom-setting}}zoom-focus.html#setzoomfactor) | Set zoom factor |

## Filter Settings

| Method | Description |
|-----------------|---------------|
| [`enableSensorControl`]({{site.ios-filter-setting}}filter.html#enablesensorcontrol) | Set true/false to turn on/off DCE sensor control. |
|[`setSensorControlThreshold`]({{site.ios-filter-setting}}filter.html#setsensorcontrolthreshold)| Make settings on sensor control threshold |
| [`enableFrameFilter`]({{site.ios-filter-setting}}filter.html#enableframefilter) | Set true/false to turn on/off DCE frame filter. |
| [`setMaxFrameRate`]({{site.ios-filter-setting}}filter.html#setmaxframerate) | Set max frame rate |