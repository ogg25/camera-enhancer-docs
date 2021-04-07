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
| [`CameraEnhancer`](initialization/initialization.md#CameraEnhancer-and-addCameraView) | Initialize Camera Enhancer object |
| [`addCameraView`](initialization/initialization.md#CameraEnhancer-and-addCameraView) | Add Camera View |
|[`initLicenseFromLTS`](initialization/initialization.md#initLicenseFromLTS)| Init license from license tracking server |
|[`getDeviceLevel`](initialization/initialization.md#getDeviceLevel)| Get device level |
|[`setApiVersion`](initialization/initialization.md#getApiVersion-and-setApiVersion)| Set API version |
|[`getApiVersion`](initialization/initialization.md#getApiVersion-and-setApiVersion)| Get current API version |
|[`setEnableBeepSound`](initialization/initialization.md#setEnableBeepSound)| Set enable beep sound true/false (Only for DBR) |
| [`updateCameraSettingFromJson`](filter-setting/filter.md#updateCameraSettingFromJson) | Update camera filter and focus settings from Json |

## Camera Setting

### Basic camera setting

| Method | Description |
|-----------------|---------------|
| [`setErrorCode`](basic-settings/basic-settings.md#setErrorCode) | Set error code |
| [`setCameraDesireState`](basic-settings/basic-settings.md#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Set Camera on/off |
| [`getCameraDesireState`](basic-settings/basic-settings.md#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera desired state |
| [`getCameraCurrentState`](basic-settings/basic-settings.md#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera current state |
| [`pauseCamera`](basic-settings/basic-settings.md#pauseCamera-and-resumeCamera) | Pause Camera |
| [`resumeCamera`](basic-settings/basic-settings.md#pauseCamera-and-resumeCamera) | Resume Camera |
| [`startScanning`](basic-settings/basic-settings.md#stopScanning-and-startScanning) | Start scanning |
| [`stopScanning`](basic-settings/basic-settings.md#stopScanning-and-startScanning) | Stop scanning |
| [`addCameraListener`](basic-settings/basic-settings.md#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) |
| [`removeCameraListener`](basic-settings/basic-settings.md#addCameraListener-and-removeCameraListener) | Remove camera listener |
| [`setTorchDesiredState`](basic-settings/basic-settings.md#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Set torch state |
| [`getTorchDesiredState`](basic-settings/basic-settings.md#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch desired state |
| [`getTorchCurrentState`](basic-settings/basic-settings.md#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch current state |
| [`addTorchListener`](basic-settings/basic-settings.md#addTorchListener) | Add torch listener |
| [`getCameraPosition`](basic-settings/basic-settings.md#getCameraPosition-and-switchCameraPosition) | Get current camera position |
| [`switchCameraPosition`](basic-settings/basic-settings.md#getCameraPosition-and-switchCameraPosition) | Switch camera position front/back |
| [`setResolution`](basic-settings/basic-settings.md#getResolution-and-setResolution) | Set resolution |
| [`getResolution`](basic-settings/basic-settings.md#getResolution-and-setResolution) | Get current resolution setting |

### Focus and Zoom setting

| Method | Description |
|-----------------|---------------|
| [`setAutoFocusAt`](zoom-setting/zoom-focus.md#setAutoFocusAt) | Set auto focus position |
| [`manualFocusOnce`](zoom-setting/zoom-focus.md#manualFocusOnce) | Set manual focus position |
| [`setForcedFocusLength`](zoom-setting/zoom-focus.md#setForcedFocusLength) | Set forced focus length |
| [`setForceAutoFocus`](zoom-setting/zoom-focus.md#setForceAutoFocus) | Set force auto focus true/false |
| [`setAutoZoom`](zoom-setting/zoom-focus.md#setAutoZoom) | Set auto zoom true/false (Only for DBR)|
| [`setZoomFactor`](zoom-setting/zoom-focus.md#setZoomFactor) | Set zoom factor |

## Filter Setting

| Method | Description |
|-----------------|---------------|
| [`setUseFrameFilter`](filter-setting/filter.md#setUseFrameFilter) | Set use frame filter true/false |
| [`setMaxFrameRate`](filter-setting/filter.md#setMaxFrameRate) | Set max frame rate |
| [`setSensorControl`](filter-setting/filter.md#setSensorControl) | Set sensor control true/false |
| [`setFastMode`](filter-setting/filter.md#setFastMode) | Set fast mode |
| [`setAutoModeLevelParam`](filter-setting/filter.md#setAutoModeLevelParam) | Set auto mode level parameter |
