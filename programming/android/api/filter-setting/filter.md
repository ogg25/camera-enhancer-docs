---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references
description: This is the documentation - Android API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references
needAutoGenerateSidebar: true
breadcrumbText: Java
---

# Dynamsoft Camera Enhancer - Android API references

## Filter Setting

- [`setUseFrameFilter`](#setUseFrameFilter)
- [`setMaxFrameRate`](#setMaxFrameRate)
- [`setSensorControl`](#setSensorControl)
- [`updateCameraSettingFromJson`](#updateCameraSettingFromJson)
- [`setFastMode`](#setFastMode)
- [`setAutoModeLevelParam`](#setAutoModeLevelParam)

### setUseFrameFilter

Turn on(off) DCE filter (recommended to be true).
```java
    mCamera.setUseFrameFilter(true);
```

### setMaxFrameRate

Set max frame rate.
```java
    try {
        mCamera.setMaxFrameRate(int);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    } 
```

### setSensorControl
    
Turn on(off) sensor control
```java
    mCamera.setSensorControl(true);
```

### updateCameraSettingFromJson

Update focus and filter settings by Json
```java
    mCamera.updateCameraSettingFromJson("Put your json String & data here");
```

### setFastMode
    
Turn on(off) fast mode. It is recommended to turned on when decoding single barcode.
```java
    mCamera.setFastMode(true);
```

### setAutoModeLevelParam
Set auto mode level parameter - cpuMHz1, cpuMHz2, ramMB1, ramMB2.
```java
    mCamera.setAutoModeLevelParam(int,int,int,int);
```
