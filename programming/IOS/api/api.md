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
| [`updateCameraSettingFromJson`](basic-settings/basic-settings.md#updateCameraSettingFromJson) | Update camera filter and focus settings from Json |
| [`updateCameraSettingFromFile`](basic-settings/basic-settings.md#updateCameraSettingFromFile) | Update camera filter and focus settings from file |
| [`enableBeepSound`](basic-settings/basic-settings.md#enableBeepSound) | Set enable beep sound true/false (Only for DBR) |

## Fast mode

| Method | Description |
|-----------------|---------------|
| [`setFastmode`](basic-settings/basic-settings.md#setFastmode) | Set fast mode |

## Camera Setting

### Basic camera setting

| Method | Description |
|-----------------|---------------|
| [`setCameraDesiredState`](basic-settings/basic-settings.md#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Set Camera on/off |
| [`getCameraDesiredState`](basic-settings/basic-settings.md#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera desired state |
| [`getCameraCurrentState`](basic-settings/basic-settings.md#getCameraCurrentState-getCameraDesireState-and-setCameraDesireState) | Get camera current state |
| [`pauseCamera`](basic-settings/basic-settings.md#pauseCamera-and-resumeCamera) | Pause Camera |
| [`resumeCamera`](basic-settings/basic-settings.md#pauseCamera-and-resumeCamera) | Resume Camera |
| [`startScanning`](basic-settings/basic-settings.md#stopScanning-and-startScanning) | Start scanning |
| [`stopScanning`](basic-settings/basic-settings.md#stopScanning-and-startScanning) | Stop scanning |
| [`addCameraListener`](basic-settings/basic-settings.md#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) | Add camera listener (on preview original, filtered or fast frames) |
| [`removeCameraListener`](basic-settings/basic-settings.md#addCameraListener-and-removeCameraListener) | Add camera listener (on preview original, filtered or fast frames) | Remove camera listener |
| [`setTorchDesiredState`](basic-settings/basic-settings.md#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Set torch state |
| [`getTorchDesiredState`](basic-settings/basic-settings.md#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch desired state |
| [`getTorchCurrentState`](basic-settings/basic-settings.md#getTorchCurrentState-getTorchDesiredState-and-setTorchDesiredState) | Get torch current state |
| [`addTorchListener`](basic-settings/basic-settings.md#addTorchListener-and-removeTorchListener) | Add torch listener |
| [`removeTorchListener`](basic-settings/basic-settings.md#addTorchListener-and-removeTorchListener) | Remove Torch Listener |
| [`getCameraPosition`](basic-settings/basic-settings.md#getCameraPosition-and-switchCameraPosition) | Get current camera position |
| [`switchCameraPosition`](basic-settings/basic-settings.md#getCameraPosition-and-switchCameraPosition) | Switch camera position front/back |
| [`setResolution`](basic-settings/basic-settings.md#getResolution-and-setResolution) | Set resolution |
| [`getResolution`](basic-settings/basic-settings.md#getResolution-and-setResolution) | Get current resolution setting |

### Focus and Zoom setting

| Method | Description |
|-----------------|---------------|
| [`setAutoFocusPoint`](zoom-setting/zoom-focus.md#setAutoFocusPoint) | Set auto focus position |
| [`manualFocusOnce`](zoom-setting/zoom-focus.md#manualFocusOnce) | Set manual focus position |
| [`setForcedFocusLength`](zoom-setting/zoom-focus.md#setForcedFocusLength) | Set forced focus length |
| [`setForceAutoFocus`](zoom-setting/zoom-focus.md#setForceAutoFocus) | Set force auto focus true/false |
| [`enableAutoZoom`](zoom-setting/zoom-focus.md#enableAutoZoom) | Turn on auto zoom |
| [`setZoomFactor`](zoom-setting/zoom-focus.md#setZoomFactor) | Set zoom factor |

## Filter Setting

| Method | Description |
|-----------------|---------------|
| [`sensorControl`](filter-setting/filter.md#setSensorControl) | Set sensor control true/false |
| [`setUseFrameFilter`](filter-setting/filter.md#setUseFrameFilter) | Set use frame filter true/false |
| [`setMaxFrameRate`](filter-setting/filter.md#setMaxFrameRate) | Set max frame rate |