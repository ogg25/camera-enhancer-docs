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

- [`enableFrameFilter`](#setUseFrameFilter)
- [`setMaxFrameRate`](#setMaxFrameRate)
- [`setFrameListLength`](#setFrameListLength)
- [`enableSensorControl`](#setSensorControl)
- [`setAutoModeLevelParam`](#setAutoModeLevelParam)

### enableFrameFilter

Turn on(off) DCE filter (recommended to be true).
```java
    mCamera.setUseFrameFilter(true);
```

### setMaxFrameRate

Set max frame rate.
```java
    try {
        mCamera.setMaxFrameRate(24);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    } 
```

### setFrameListLength

Filtered frame will be stored in a list for decoding process. Decoder will always get the newest frame for decoding.
```java
    try {
        //The default length of frame list will be 10 if you don't make any setting on it.
        mCamera.setFrameListLength(8);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    } 
```

### enableSensorControl
    
Two parameters are required in this API. Please use true(false) to turn on(off) sensor control and fill in a threshold for sensor filter.

```java
    mCamera.enableSensorControl(true, 50);
```

### setAutoModeLevelParam
Set auto mode level parameter - cpuMHz1, cpuMHz2, ramMB1, ramMB2.
```java
    mCamera.setAutoModeLevelParam(int,int,int,int);
```
