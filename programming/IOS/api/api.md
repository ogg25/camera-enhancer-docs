---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references
description: This is the documentation - Objective-C & Swift API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references
needAutoGenerateSidebar: true
breadcrumbText: Objective-C & Swift (IOS)
---

# Dynamsoft Camera Enhancer - Objective-C & Swift API references

- [Initialization](#Initialization-License-and-other-basic-settings)
- [Camera Setting](#Camera-Setting)
    - [Basic Camera Setting](#Basic-camera-setting)
    - [Focus & Zoom Setting](#Focus-and-Zoom-setting)
- [Filter Setting](#Filter-Setting)
## Initialization, License and other basic settings

| Method | Description |
|-----------------|---------------|
| [`updateCameraSettingFromJson`]({{site.ios-basic-setting}}basic-settings.html#updateCameraSettingFromJson) | Update camera filter and focus settings from Json |
| [`updateCameraSettingFromFile`]({{site.ios-basic-setting}}basic-settings.html#updateCameraSettingFromFile) | Update camera filter and focus settings from file |
| [`enableBeepSound`]({{site.ios-basic-setting}}basic-settings.html#enableBeepSound) | Set enable beep sound true/false (Only for DBR) |

## Fast mode

| Method | Description |
|-----------------|---------------|
| [`setFastmode`]({{site.ios-basic-setting}}basic-settings.html#setFastmode) | Set fast mode |

## Camera Setting

### Basic camera setting

| Method | Description |
|-----------------|---------------|
| [`setCameraDesiredState`]({{site.ios-basic-setting}}basic-settings.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Set Camera on/off |
| [`getCameraDesiredState`]({{site.ios-basic-setting}}basic-settings.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera desired state |
| [`getCameraCurrentState`]({{site.ios-basic-setting}}basic-settings.html#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera current state |
| [`pauseCamera`]({{site.ios-basic-setting}}basic-settings.html#pauseCamera-and-resumeCamera) | Pause Camera |
| [`resumeCamera`]({{site.ios-basic-setting}}basic-settings.html#pauseCamera-and-resumeCamera) | Resume Camera |
| [`startScanning`]({{site.ios-basic-setting}}basic-settings.html#stopScanning-and-startScanning) | Start scanning |
| [`stopScanning`]({{site.ios-basic-setting}}basic-settings.html#stopScanning-and-startScanning) | Stop scanning |
| [`addCameraListener`]({{site.ios-basic-setting}}basic-settings.html#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) | Add camera listener (on preview original, filtered or fast frames) |
| [`removeCameraListener`]({{site.ios-basic-setting}}basic-settings.html#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) | Remove camera listener |
| [`setTorchDesiredState`]({{site.ios-basic-setting}}basic-settings.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Set torch state |
| [`getTorchDesiredState`]({{site.ios-basic-setting}}basic-settings.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch desired state |
| [`getTorchCurrentState`]({{site.ios-basic-setting}}basic-settings.html#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch current state |
| [`addTorchListener`]({{site.ios-basic-setting}}basic-settings.html#addTorchListener-and-removeTorchListener) | Add torch listener |
| [`removeTorchListener`]({{site.ios-basic-setting}}basic-settings.html#addTorchListener-and-removeTorchListener) | Remove Torch Listener |
| [`getCameraPosition`]({{site.ios-basic-setting}}basic-settings.html#getCameraPosition-and-switchCameraPosition) | Get current camera position |
| [`switchCameraPosition`]({{site.ios-basic-setting}}basic-settings.html#getCameraPosition-and-switchCameraPosition) | Switch camera position front/back |
| [`setResolution`]({{site.ios-basic-setting}}basic-settings.html#getResolution-and-setResolution) | Set resolution |
| [`getResolution`]({{site.ios-basic-setting}}basic-settings.html#getResolution-and-setResolution) | Get current resolution setting |

### Focus and Zoom setting

| Method | Description |
|-----------------|---------------|
| [`setAutoFocusPoint`]({{site.ios-zoom-setting}}zoom-focus.html#setAutoFocusPoint) | Set auto focus position |
| [`manualFocusOnce`]({{site.ios-zoom-setting}}zoom-focus.html#manualFocusOnce) | Set manual focus position |
| [`setForcedFocusLength`]({{site.ios-zoom-setting}}zoom-focus.html#setForcedFocusLength) | Set forced focus length |
| [`setForceAutoFocus`]({{site.ios-zoom-setting}}zoom-focus.html#setForceAutoFocus) | Set force auto focus true/false |
| [`enableAutoZoom`]({{site.ios-zoom-setting}}zoom-focus.html#enableAutoZoom) | Turn on auto zoom |
| [`setZoomFactor`]({{site.ios-zoom-setting}}zoom-focus.html#setZoomFactor) | Set zoom factor |

## Filter Setting

| Method | Description |
|-----------------|---------------|
| [`sensorControl`]({{site.ios-filter-setting}}filter.html#setSensorControl) | Set sensor control true/false |
| [`setUseFrameFilter`]({{site.ios-filter-setting}}filter.html#setUseFrameFilter) | Set use frame filter true/false |
| [`setMaxFrameRate`]({{site.ios-filter-setting}}filter.html#setMaxFrameRate) | Set max frame rate |