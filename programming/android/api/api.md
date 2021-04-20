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
- [Camera Setting](#Camera-Setting)
    - [Basic Camera Setting](#Basic-camera-setting)
    - [Focus & Zoom Setting](#Focus-and-Zoom-setting)
- [Filter Setting](#Filter-Setting)

## Initialization, License and other basic settings

| Method | Description |
|-----------------|---------------|
|[`getDeviceLevel`]({{site.android-basic-setting}}basic-setting.html#getDeviceLevel)| Get device level. |
|[`setApiVersion`]({{site.android-basic-setting}}basic-setting.html#getApiVersion-and-setApiVersion)| Set API version. |
|[`getApiVersion`]({{site.android-basic-setting}}basic-setting.html#getApiVersion-and-setApiVersion)| Get current API version. |
| [`updateCameraSetting`]({{site.android-basic-setting}}basic-setting.html#updateCameraSetting) | Update camera filter and focus settings from Json. |

## Fast mode

| Method | Description |
|-----------------|---------------|
| [`enableFastMode`]({{site.android-basic-setting}}basic-setting.html#enableFastMode) | Enable fast mode (true/false). |

## Camera Setting

### Basic camera setting

| Method | Description |
|-----------------|---------------|
| [`setErrorCode`]({{site.android-basic-setting}}basic-setting.html#setErrorCode) | Set error code. |
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

### Focus and Zoom setting

| Method | Description |
|-----------------|---------------|
| [`enableAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#enableAutoFocus) | Enable auto focus (true/false). |
| [`setAutoFocusAt`]({{site.android-zoom-setting}}zoom-focus.html#setAutoFocusPoint) | Set auto focus position. |
| [`setManualFocusAt`]({{site.android-zoom-setting}}zoom-focus.html#setManualFocusAt) | Set manual focus position. |
| [`setFocalLength`]({{site.android-zoom-setting}}zoom-focus.html#setFocalLength) | Set focal length. |
| [`enableRegularAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#enableRegularAutoFocus) | Enable auto focus for every 3 seconds. |
| [`enableAutoFocusOnSharpnessChange`]({{site.android-zoom-setting}}zoom-focus.html#enableAutoFocusOnSharpnessChange) | Enable camera to focus when clarity changes. |
| [`enableAutoZoom`]({{site.android-zoom-setting}}zoom-focus.html#enableAutoZoom) | Enable auto zoom (true/false). |
| [`setZoomFactor`]({{site.android-zoom-setting}}zoom-focus.html#setZoomFactor) | Set zoom factor. |


## Filter Setting

| Method | Description |
|-----------------|---------------|
| [`enableFrameFilter`]({{site.android-filter-setting}}filter.html#enableFrameFilter) | Enable frame filter (true/false). |
| [`setMaxFrameRate`]({{site.android-filter-setting}}filter.html#setMaxFrameRate) | Set max frame rate. |
| [`setFrameListLength`]({{site.android-filter-setting}}filter.html#setFrameListLength) | Set how many frames will be stored in list. |
| [`enableSensorControl`]({{site.android-filter-setting}}filter.html#enableSensorControl) | Enable sensor control (true/false). |
| [`setAutoModeLevelParam`]({{site.android-filter-setting}}filter.html#setAutoModeLevelParam) | Set auto mode level parameter. |

## Class

- [`CameraEnhancerException`]()
- [`CameraLTSConnectionParameters`]()
- [`Frame`]()