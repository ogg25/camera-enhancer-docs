---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references - Filter Setting
description: This is the documentation - Android API references - Filter Setting page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references, Filter
needAutoGenerateSidebar: true
breadcrumbText: Android Filter Setting
---

# Android API Reference - Filter Setting

- [`enableFrameFilter`](#enableframefilter)
- [`getEnabledFrameFilterStatus`](#enableframefilter)
- [`setMaxFrameRate`](#setmaxframerate)
- [`enableSensorControl`](#enablesensorcontrol)
- [`getEnabledSensorControlStatus`](#enablesensorcontrol)
- [`setSensorControlThreshold`](#setsensorcontrolthreshold)

## enableFrameFilter

Use `enableFrameFilter` to turn on/off frame filter.

```java
    mCamera.enableFrameFilter(true);
```

To check the status of frame filter mode, please use `getEnabledFrameFilterStatus`

```java
    boolean x = mCamera.getEnabledFrameFilterStatus();
```

## setMaxFrameRate

Set max frame rate.

```java
    mCamera.setMaxFrameRate(24);
```

## enableSensorControl

Use `enableSensorControl` to turn on/off sensor control mode.

```java
    mCamera.enableSensorControl(true);
```

To check the status of sensor control mode, please use `getEnabledSensorControlStatus`

```java
    boolean x = mCamera.getEnabledSensorControlStatus();
```

## setSensorControlThreshold

This API is designed for developers to apply different sensor sensitivity settings on different devices. The default value is 50.

```java
    mCamera.setSensorControlThreshold(55);
```
