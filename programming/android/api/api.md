---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references
description: This is the documentation - Android API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references
needAutoGenerateSidebar: true
breadcrumbText: Android API References
---

# Android API References

- [Initialization](#initialization)
- [Fast Mode](#fast-mode)
- [Basic Camera Settings](#basic-camera-settings)
- [Focus Settings](#focus-settings)
- [Zoom Settings](#zoom-settings)
- [Filter Setting](#filter-settings)

## Initialization

| Method | Description |
|-----------------|---------------|
|[`getDeviceLevel`]({{site.android-basic-setting}}basic-setting.html#getdevicelevel)| Make a evaluation on the current device and define its level for further use. |
| [`setAutoModeLevelParam`]({{site.android-filter-setting}}filter.html#setautomodelevelparam) | Set auto mode level parameter. |
| [`updateCameraSetting`]({{site.android-basic-setting}}basic-setting.html#updatecamerasetting) | Update camera filter and focus settings from Json. |
| [`getVersion`]({{site.android-basic-setting}}basic-setting.html#getversion) | Check current DCE version |

## Fast mode

| Method | Description |
|-----------------|---------------|
| [`enableFastMode`]({{site.android-basic-setting}}basic-setting.html#fast-mode) | Set true/false to turn on/off DCE fast mode. |
| [`getEnabledFastModeStatus`]({{site.android-basic-setting}}basic-setting.html#fast-mode) | Get the current status of fast mode (on/off). |

## Basic Camera Settings

| Method | Description |
|-----------------|---------------|
| [`setCameraDesiredState`]({{site.android-basic-setting}}basic-setting.html#camera-state) | Set Camera on/off. |
| [`getCameraDesiredState`]({{site.android-basic-setting}}basic-setting.html#camera-state) | Get camera desired state. |
| [`getCameraCurrentState`]({{site.android-basic-setting}}basic-setting.html#camera-state) | Get camera current state. |
| [`pauseCamera`]({{site.android-basic-setting}}basic-setting.html#pausecamera-and-resumecamera) | Pause Camera. |
| [`resumeCamera`]({{site.android-basic-setting}}basic-setting.html#pausecamera-and-resumecamera) | Resume Camera. |
| [`startScanning`]({{site.android-basic-setting}}basic-setting.html#stopscanning-and-startscanning) | Start scanning. |
| [`stopScanning`]({{site.android-basic-setting}}basic-setting.html#stopscanning-and-startscanning) | Stop scanning. |
| [`addCameraListener`]({{site.android-basic-setting}}basic-setting.html#addcameralistener) | Add camera listener (on preview original, filtered or fast frames). |
| [`removeCameraListener`]({{site.android-basic-setting}}basic-setting.html#addcameralistener) | Remove camera listener. |
| [`setTorchDesiredState`]({{site.android-basic-setting}}basic-setting.html#torch-state) | Set torch state. |
| [`getTorchDesiredState`]({{site.android-basic-setting}}basic-setting.html#torch-state) | Get torch desired state. |
| [`getTorchCurrentState`]({{site.android-basic-setting}}basic-setting.html#torch-state) | Get torch current state. |
| [`addTorchListener`]({{site.android-basic-setting}}basic-setting.html#addtorchlistener) | Add torch listener. |
| [`getCameraPosition`]({{site.android-basic-setting}}basic-setting.html#camera-position) | Get current camera position. |
| [`switchCameraPosition`]({{site.android-basic-setting}}basic-setting.html#camera-position) | Switch camera position front/back. |
| [`setResolution`]({{site.android-basic-setting}}basic-setting.html#resolution-settings) | Set resolution. |
| [`getResolution`]({{site.android-basic-setting}}basic-setting.html#resolution-settings) | Get current resolution setting. |
| [`getResolutionList`]({{site.android-basic-setting}}basic-setting.html#resolution-settings) | Get all available resolutions |

## Focus Settings

Focus parameters related APIs:

| Method | Description |
|-----------------|---------------|
| [`setAutoFocusPosition`]({{site.android-zoom-setting}}zoom-focus.html#setautofocusposition) | Set auto focus position (Change the default auto focus position). |
| [`setManualFocusPosition`]({{site.android-zoom-setting}}zoom-focus.html#setmanualfocusposition) | Set manual focus position (This focus position only effect once for each time the API is called). |
| [`setFocalLength`]({{site.android-zoom-setting}}zoom-focus.html#setfocallength) | Set focal length between 0 to 10 to enable fixed focal length mode. In fixed focal length mode, all focus parameters can't be changed until this mode is quitted. To quit fixed focal length mode, please set focal length equals to -1. |

Basic focus settings:

| Method | Description |
|-----------------|---------------|
| [`enableDCEAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#enabledceautofocus) | Set true/false to turn on/off DCE auto focus. |
| [`getEnabledDCEAutoFocusStatus`]({{site.android-zoom-setting}}zoom-focus.html#enabledceautofocus) | Get the status (on/off) of DCE auto focus. |
| [`enableDefaultAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#enabledefaultautofocus) | Set true/false to turn on/off default auto focus. |
| [`getEnabledDefaultAutoFocusStatus`]({{site.android-zoom-setting}}zoom-focus.html#enabledefaultautofocus) | Get the status (on/off) of camera default auto focus. |

Advanced focus settings:

| Method | Description |
|-----------------|---------------|
| [`enableRegularAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#enableregularautofocus) | If this is true, camera will autofocus for every 3 seconds. This focus mode will start automatically if DCE autofocus is enabled. Users can manually quit this focus mode when DCE autofocus is activated. |
| [`getEnabledRegularAutoFocusStatus`]({{site.android-zoom-setting}}zoom-focus.html#enableregularautofocus) | Get the current status (on/off) of this auto focus mode. |
| [`enableAutoFocusOnSharpnessChange`]({{site.android-zoom-setting}}zoom-focus.html#enableautofocusonsharpnesschange) | If this is enabled, camera will autofocus when clarity change is detected. This focus mode will start automatically if DCE autofocus is enabled. Users can manually quit this focus mode when DCE autofocus is activated. |
| [`getEnabledAutoFocusOnSharpnessChangeStatus`]({{site.android-zoom-setting}}zoom-focus.html#enableautofocusonsharpnesschange) | Get the current status (on/off) of this auto focus mode. |

## Zoom Settings

| Method | Description |
|-----------------|---------------|
| [`enableAutoZoom`]({{site.android-zoom-setting}}zoom-focus.html#enableautozoom) | Set enableAutoZoom value true to enable auto zoom mode. |
| [`getEnabledAutoZoomStatus`]({{site.android-zoom-setting}}zoom-focus.html#enableautozoom) | Get the status (on/off) of auto zoom mode. |
| [`setZoomFactor`]({{site.android-zoom-setting}}zoom-focus.html#setzoomfactor) | Set zoom factor. |

## Filter Settings

| Method | Description |
|-----------------|---------------|
| [`enableFrameFilter`]({{site.android-filter-setting}}filter.html#enableframefilter) | Set true/false to turn on/off DCE frame filter. |
| [`getEnabledFrameFilterStatus`]({{site.android-filter-setting}}filter.html#enableframefilter) | Get the status (on/off) of DCE frame filter mode. |
| [`setMaxFrameRate`]({{site.android-filter-setting}}filter.html#setmaxframerate) | Set max frame rate. |
| [`enableSensorControl`]({{site.android-filter-setting}}filter.html#enablesensorcontrol) | Set true/false to turn on/off DCE sensor control. |
| [`getEnabledSensorControlStatus`]({{site.android-filter-setting}}filter.html#enablesensorcontrol) | Get the status (on/off) of DCE sensor control mode. |
| [`setSensorControlThreshold`]({{site.android-filter-setting}}filter.html#setsensorcontrolthreshold) | Enable user to change sensor sensitivity (default value is 50). |
