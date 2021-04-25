---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references
description: This is the documentation - Android API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references
needAutoGenerateSidebar: true
breadcrumbText: Android API References
---

# Android API References

- [Initialization](#Initialization-License-and-other-basic-settings)
- [Basic Camera Settings](#Basic-Camera-Settings)
- [Focus Settings](#Focus-Settings)
- [Zoom Settings](#Zoom-Settings)
- [Filter Setting](#Filter-Settings)

## Initialization, License and other basic settings

| Method | Description |
|-----------------|---------------|
|[`getDeviceLevel`]({{site.android-basic-setting}}basic-setting.html#getDeviceLevel)| Make a evaluation on the current device and define its level for further use. |
|[`getApiVersion`]({{site.android-basic-setting}}basic-setting.html#getApiVersion-and-setApiVersion)| Get current API version. |
| [`updateCameraSetting`]({{site.android-basic-setting}}basic-setting.html#updateCameraSetting) | Update camera filter and focus settings from Json. |

## Fast mode

| Method | Description |
|-----------------|---------------|
| [`enableFastMode`]({{site.android-basic-setting}}basic-setting.html#FastMode) | Set true/false to turn on/off DCE fast mode. |
| [`getEnableFastModeStatus`]({{site.android-basic-setting}}basic-setting.html#FastMode) | Get the current status of fast mode (on/off). |

## Basic Camera Settings

| Method | Description |
|-----------------|---------------|
| [`setCameraDesiredState`]({{site.android-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Set Camera on/off. |
| [`getCameraDesiredState`]({{site.android-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera desired state. |
| [`getCameraCurrentState`]({{site.android-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera current state. |
| [`pauseCamera`]({{site.android-basic-setting}}basic-setting.html#pauseCamera-and-resumeCamera) | Pause Camera. |
| [`resumeCamera`]({{site.android-basic-setting}}basic-setting.html#pauseCamera-and-resumeCamera) | Resume Camera. |
| [`startScanning`]({{site.android-basic-setting}}basic-setting.html#stopScanning-and-startScanning) | Start scanning. |
| [`stopScanning`]({{site.android-basic-setting}}basic-setting.html#stopScanning-and-startScanning) | Stop scanning. |
| [`addCameraListener`]({{site.android-basic-setting}}basic-setting.html#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames). |
| [`removeCameraListener`]({{site.android-basic-setting}}basic-setting.html#addCameraListener-and-removeCameraListener) | Remove camera listener. |
| [`setTorchDesiredState`]({{site.android-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Set torch state. |
| [`getTorchDesiredState`]({{site.android-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch desired state. |
| [`getTorchCurrentState`]({{site.android-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch current state. |
| [`addTorchListener`]({{site.android-basic-setting}}basic-setting.html#addTorchListener) | Add torch listener. |
| [`getCameraPosition`]({{site.android-basic-setting}}basic-setting.html#getCameraPosition-and-switchCameraPosition) | Get current camera position. |
| [`switchCameraPosition`]({{site.android-basic-setting}}basic-setting.html#getCameraPosition-and-switchCameraPosition) | Switch camera position front/back. |
| [`setResolution`]({{site.android-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Set resolution. |
| [`getResolution`]({{site.android-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Get current resolution setting. |
| [`getResolutionList`]({{site.android-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Get all available resolutions |

## Focus Settings

Focus parameters related APIs:
| Method | Description |
|-----------------|---------------|
| [`setAutoFocusPosition`]({{site.android-zoom-setting}}zoom-focus.html#setAutoFocusPoint) | Set auto focus position (Change the default auto focus position). |
| [`setManualFocusPosition`]({{site.android-zoom-setting}}zoom-focus.html#setManualFocusAt) | Set manual focus position (This focus position only effect once for each time the API is called). |
| [`setFocalLength`]({{site.android-zoom-setting}}zoom-focus.html#setFocalLength) | Set focal length between 0 to 10 to enable fixed focal length mode. In fixed focal length mode, all focus parameters can't be changed until this mode is quit. To quit fixed focal length mode, please set focal length equals to -1. |

Basic focus settings: 
| Method | Description |
|-----------------|---------------|
| [`enableDCEAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#enableDCEAutoFocus) | Set true/false to turn on/off DCE auto focus. |
| [`getEnableDCEAutoFocusStatus`]({{site.android-zoom-setting}}zoom-focus.html#enableDCEAutoFocus) | Get the status (on/off) of DCE auto focus. |
| [`enableDefaultAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#enableDefaultAutoFocus) | Set true/false to turn on/off default auto focus. |
| [`getEnableDefaultAutoFocusStatus`]({{site.android-zoom-setting}}zoom-focus.html#enableDefaultAutoFocus) | Get the status (on/off) of camera default auto focus. |

Advanced focus settings: 
| Method | Description |
|-----------------|---------------|
| [`enableRegularAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#enableRegularAutoFocus) | If this is true, camera will auto focus for every 3 seconds. This focus mode will start automatically if DCE auto focus is enabled. Users can manually quit this focus mode when DCE auto focus is activated. |
| [`getEnableRegularAutoFocusStatus`]({{site.android-zoom-setting}}zoom-focus.html#enableRegularAutoFocus) | Get the current status (on/off) of this auto focus mode. |
| [`enableAutoFocusOnSharpnessChange`]({{site.android-zoom-setting}}zoom-focus.html#enableAutoFocusOnSharpnessChange) | If this is enabled, camera will auto focus when clarity change is detected. This focus mode will start automatically if DCE auto focus is enabled. Users can manually quit this focus mode when DCE auto focus is activated. |
| [`getEnableAutoFocusOnSharpnessChangeStatus`]({{site.android-zoom-setting}}zoom-focus.html#enableAutoFocusOnSharpnessChange) | Get the current status (on/off) of this auto focus mode. |

## Zoom Settings

| Method | Description |
|-----------------|---------------|
| [`enableAutoZoom`]({{site.android-zoom-setting}}zoom-focus.html#AutoZoom) | Set enableAutoZoom value true to enable auto zoom mode. |
| [`getEnableAutoZoomStatus`]({{site.android-zoom-setting}}zoom-focus.html#AutoZoom) | Get the status (on/off) of auto zoom mode. |
| [`setZoomFactor`]({{site.android-zoom-setting}}zoom-focus.html#setZoomFactor) | Set zoom factor. |

## Filter Settings

| Method | Description |
|-----------------|---------------|
| [`enableFrameFilter`]({{site.android-filter-setting}}filter.html#FrameFilter) | Set true/false to turn on/off DCE frame filter. |
| [`getEnableFrameFilterStatus`]({{site.android-filter-setting}}filter.html#FrameFilter) | Get the status (on/off) of DCE frame filter mode. |
| [`setMaxFrameRate`]({{site.android-filter-setting}}filter.html#setMaxFrameRate) | Set max frame rate. |
| [`setFrameListLength`]({{site.android-filter-setting}}filter.html#setFrameListLength) | Set how many frames will be stored in list. |
| [`enableSensorControl`]({{site.android-filter-setting}}filter.html#SensorControl) | Set true/false to turn on/off DCE sensor control. |
| [`getEnableSensorControlStatus`]({{site.android-filter-setting}}filter.html#SensorControl) | Get the status (on/off) of DCE sensor control mode. |
| [`setSensorControlThreshold`]({{site.android-filter-setting}}filter.html#setSensorControlThreshold) | Enable user to change sensor sensitivity (default value is 50). |
| [`setAutoModeLevelParam`]({{site.android-filter-setting}}filter.html#setAutoModeLevelParam) | Set auto mode level parameter. |