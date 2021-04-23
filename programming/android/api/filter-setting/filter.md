---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references - Filter Setting
description: This is the documentation - Android API references - Filter Setting page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references, Filter
needAutoGenerateSidebar: true
breadcrumbText: Android Filter Setting
---

# Android API Reference - Filter Setting

- [`enableFrameFilter`](#FrameFilter)
- [`setMaxFrameRate`](#setMaxFrameRate)
- [`setFrameListLength`](#setFrameListLength)
- [`enableSensorControl`](#SensorControl)
- [`setAutoModeLevelParam`](#setAutoModeLevelParam)

## enableFrameFilter

Use `enableFrameFilter` to turn on/off frame filter. 
```java
    mCamera.enableFrameFilter(true);
```
To check the status of frame filter mode, please use `getEnableFrameFilterStatus`
```java
    boolean x = mCamera.getEnableFrameFilterStatus();
```

## setMaxFrameRate

Set max frame rate.
```java
    mCamera.setMaxFrameRate(24);
```

## setFrameListLength

Filtered frame will be stored in a list for decoding process. Decoder will always get the newest frame for decoding.
```java
    //The default length of frame list will be 10 if you don't make any setting on it.
    mCamera.setFrameListLength(8);
```

## enableSensorControl

Use `enableSensorControl` to turn on/off sensor control mode. 
```java
    mCamera.enableSensorControl(true);
```
To check the status of sensor control mode, please use `getEnableSensorControlStatus`
```java
    boolean x = mCamera.getEnableSensorControlStatus();
```

## setSensorControlThreshold

This API is designed for developers to apply different sensor sensitivity settings on different devices. The default value is 50 if user don't make any change.
```java
    mCamera.setSensorControlThreshold(55);
```

## setAutoModeLevelParam
Set auto mode level parameter - cpuMHz1, cpuMHz2, ramMB1, ramMB2.
```java
    mCamera.setAutoModeLevelParam(int,int,int,int);
```
