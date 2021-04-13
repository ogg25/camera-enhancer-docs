---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references
description: This is the documentation - Android API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references
needAutoGenerateSidebar: true
breadcrumbText: Java
---

# Dynamsoft Camera Enhancer - Android API references
- [Initialization](#Initialization-License-and-other-basic-settings)
- [Camera Setting](#Camera-Setting)
    - [Basic Camera Setting](#Basic-camera-setting)
    - [Focus & Zoom Setting](#Focus-and-Zoom-setting)
- [Filter Setting](#Filter-Setting)

## Initialization, License and other basic settings

| Method | Description |
|-----------------|---------------|
|[`getDeviceLevel`]({{site.android-basic-setting}}basic-setting.html#getDeviceLevel)| Get device level |
|[`setApiVersion`]({{site.android-basic-setting}}basic-setting.html#getApiVersion-and-setApiVersion)| Set API version |
|[`getApiVersion`]({{site.android-basic-setting}}basic-setting.html#getApiVersion-and-setApiVersion)| Get current API version |
|[`setEnableBeepSound`]({{site.android-basic-setting}}basic-setting.html#setEnableBeepSound)| Set enable beep sound true/false (Only for DBR) |
| [`updateCameraSettingFromJson`]({{site.android-basic-setting}}basic-setting.html#updateCameraSettingFromJson) | Update camera filter and focus settings from Json |
| [`updateCameraSettingFromFile`]({{site.android-basic-setting}}basic-setting.html#updateCameraSettingFromFile) | Update camera filter and focus settings from file |

## Camera Setting

### Basic camera setting

| Method | Description |
|-----------------|---------------|
| [`setErrorCode`]({{site.android-basic-setting}}basic-setting.html#setErrorCode) | Set error code |
| [`setCameraDesiredState`]({{site.android-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Set Camera on/off |
| [`getCameraDesiredState`]({{site.android-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera desired state |
| [`getCameraCurrentState`]({{site.android-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera current state |
| [`pauseCamera`]({{site.android-basic-setting}}basic-setting.html#pauseCamera-and-resumeCamera) | Pause Camera |
| [`resumeCamera`]({{site.android-basic-setting}}basic-setting.html#pauseCamera-and-resumeCamera) | Resume Camera |
| [`startScanning`]({{site.android-basic-setting}}basic-setting.html#stopScanning-and-startScanning) | Start scanning |
| [`stopScanning`]({{site.android-basic-setting}}basic-setting.html#stopScanning-and-startScanning) | Stop scanning |
| [`addCameraListener`]({{site.android-basic-setting}}basic-setting.html#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) |
| [`removeCameraListener`]({{site.android-basic-setting}}basic-setting.html#addCameraListener-and-removeCameraListener) | Remove camera listener |
| [`setTorchDesiredState`]({{site.android-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Set torch state |
| [`getTorchDesiredState`]({{site.android-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch desired state |
| [`getTorchCurrentState`]({{site.android-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch current state |
| [`addTorchListener`]({{site.android-basic-setting}}basic-setting.html#addTorchListener) | Add torch listener |
| [`getCameraPosition`]({{site.android-basic-setting}}basic-setting.html#getCameraPosition-and-switchCameraPosition) | Get current camera position |
| [`switchCameraPosition`]({{site.android-basic-setting}}basic-setting.html#getCameraPosition-and-switchCameraPosition) | Switch camera position front/back |
| [`setResolution`]({{site.android-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Set resolution |
| [`getResolution`]({{site.android-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Get current resolution setting |

### Focus and Zoom setting

| Method | Description |
|-----------------|---------------|
| [`setAutoFocusAt`]({{site.android-zoom-setting}}zoom-focus.html#setAutoFocusAt) | Set auto focus position |
| [`manualFocusOnce`]({{site.android-zoom-setting}}zoom-focus.html#manualFocusOnce) | Set manual focus position |
| [`setForcedFocusLength`]({{site.android-zoom-setting}}zoom-focus.html#setForcedFocusLength) | Set forced focus length |
| [`setForceAutoFocus`]({{site.android-zoom-setting}}zoom-focus.html#setForceAutoFocus) | Set force auto focus true/false |
| [`setAutoZoom`]({{site.android-zoom-setting}}zoom-focus.html#setAutoZoom) | Set auto zoom true/false (Only for DBR)|
| [`setZoomFactor`]({{site.android-zoom-setting}}zoom-focus.html#setZoomFactor) | Set zoom factor |

## Filter Setting

| Method | Description |
|-----------------|---------------|
| [`setUseFrameFilter`]({{site.android-filter-setting}}filter.html#setUseFrameFilter) | Set use frame filter true/false |
| [`setMaxFrameRate`]({{site.android-filter-setting}}filter.html#setMaxFrameRate) | Set max frame rate |
| [`setSensorControl`]({{site.android-filter-setting}}filter.html#setSensorControl) | Set sensor control true/false |
| [`setFastMode`]({{site.android-filter-setting}}filter.html#setFastMode) | Set fast mode |
| [`setAutoModeLevelParam`]({{site.android-filter-setting}}filter.html#setAutoModeLevelParam) | Set auto mode level parameter |
