---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references
description: This is the documentation - Objective-C & Swift API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references
needAutoGenerateSidebar: true
breadcrumbText: iOS API Reference
---

# Objective-C & Swift (iOS) API references

- [Initialization](#Initialization-License-and-other-basic-settings)
- [Camera Setting](#Camera-Setting)
    - [Basic Camera Setting](#Basic-camera-setting)
    - [Focus & Zoom Setting](#Focus-and-Zoom-setting)
- [Filter Setting](#Filter-Setting)
## Initialization, License and other basic settings

| Method | Description |
|-----------------|---------------|
| [`updateCameraSettingFromJson`]({{site.ios-basic-setting}}basic-setting.html#updateCameraSettingFromJson) | Update camera filter and focus settings from Json |
| [`updateCameraSettingFromFile`]({{site.ios-basic-setting}}basic-setting.html#updateCameraSettingFromFile) | Update camera filter and focus settings from file |

## Fast mode

| Method | Description |
|-----------------|---------------|
| [`enableFastMode`]({{site.ios-basic-setting}}basic-setting.html#setFastmode) | Enable fast mode (true/false) |

## Camera Setting

### Basic camera setting

| Method | Description |
|-----------------|---------------|
| [`setCameraDesiredState`]({{site.ios-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Set Camera on/off |
| [`getCameraDesiredState`]({{site.ios-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera desired state |
| [`getCameraCurrentState`]({{site.ios-basic-setting}}basic-setting.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera current state |
| [`pauseCamera`]({{site.ios-basic-setting}}basic-setting.html#pauseCamera-and-resumeCamera) | Pause Camera |
| [`resumeCamera`]({{site.ios-basic-setting}}basic-setting.html#pauseCamera-and-resumeCamera) | Resume Camera |
| [`startScanning`]({{site.ios-basic-setting}}basic-setting.html#stopScanning-and-startScanning) | Start scanning |
| [`stopScanning`]({{site.ios-basic-setting}}basic-setting.html#stopScanning-and-startScanning) | Stop scanning |
| [`addCameraListener`]({{site.ios-basic-setting}}basic-setting.html#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) | Add camera listener (on preview original, filtered or fast frames) |
| [`removeCameraListener`]({{site.ios-basic-setting}}basic-setting.html#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) | Remove camera listener |
| [`setTorchDesiredState`]({{site.ios-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Set torch state |
| [`getTorchDesiredState`]({{site.ios-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch desired state |
| [`getTorchCurrentState`]({{site.ios-basic-setting}}basic-setting.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch current state |
| [`addTorchListener`]({{site.ios-basic-setting}}basic-setting.html#addTorchListener-and-removeTorchListener) | Add torch listener |
| [`removeTorchListener`]({{site.ios-basic-setting}}basic-setting.html#addTorchListener-and-removeTorchListener) | Remove Torch Listener |
| [`getCameraPosition`]({{site.ios-basic-setting}}basic-setting.html#getCameraPosition-and-switchCameraPosition) | Get current camera position |
| [`switchCameraPosition`]({{site.ios-basic-setting}}basic-setting.html#getCameraPosition-and-switchCameraPosition) | Switch camera position front/back |
| [`setResolution`]({{site.ios-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Set resolution |
| [`getResolution`]({{site.ios-basic-setting}}basic-setting.html#getResolution-and-setResolution) | Get current resolution setting |

### Focus and Zoom setting

| Method | Description |
|-----------------|---------------|
| [`enableAutoFocus`]({{site.ios-zoom-setting}}zoom-focus.html#enableAutoFocus) | Enable auto focus (true/false) |
| [`setAutoFocusAt`]({{site.ios-zoom-setting}}zoom-focus.html#setAutoFocusPoint) | Set auto focus position |
| [`setManualFocusAt`]({{site.ios-zoom-setting}}zoom-focus.html#setManualFocusAt) | Set manual focus position |
| [`setFocalLength`]({{site.ios-zoom-setting}}zoom-focus.html#setFocalLength) | Set focal length |
| [`enableRegularAutoFocus`]({{site.ios-zoom-setting}}zoom-focus.html#enableRegularAutoFocus) | Enable auto focus for every 3 seconds |
| [`enableAutoFocusOnSharpnessChange`]({{site.ios-zoom-setting}}zoom-focus.html#enableAutoFocusOnSharpnessChange) | Enable camera to focus when clarity changes |
| [`enableAutoZoom`]({{site.ios-zoom-setting}}zoom-focus.html#enableAutoZoom) | Enable auto zoom (true/false) |
| [`setZoomFactor`]({{site.ios-zoom-setting}}zoom-focus.html#setZoomFactor) | Set zoom factor |

## Filter Setting

| Method | Description |
|-----------------|---------------|
| [`enableSensorControl`]({{site.ios-filter-setting}}filter.html#setSensorControl) | Enable sensor control (true/false) |
| [`enableFrameFilter`]({{site.ios-filter-setting}}filter.html#setUseFrameFilter) | Enable use frame filter (true/false) |
| [`setMaxFrameRate`]({{site.ios-filter-setting}}filter.html#setMaxFrameRate) | Set max frame rate |
| [`setFrameListLength`]({{site.ios-filter-setting}}filter.html#setFrameListLength) | Set how many frames will be stored in list. |

## Class

- [`CameraEnhancerException`]()
- [`CameraException`]()
- [`CameraLTSConnectionParameters`]()
- [`CameraView`]()
- [`DCEUsage`]()
- [`Frame`]()
- [`HardwareUtil`]()
- [`Resolution`]()
- [`TorchListener`]()
- [`TorchState`]()