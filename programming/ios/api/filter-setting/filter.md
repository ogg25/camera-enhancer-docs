---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references - Filter setting
description: This is the documentation - Objective-C & Swift API references - Filter setting page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift, API references, Filter
needAutoGenerateSidebar: true
breadcrumbText: iOS Filter Setting
---

# iOS API Reference - Filter Setting

- [`enableSensorControl`](#enablesensorcontrol)
- [`setSensorControlThreshold`](#setsensorcontrolthreshold)
- [`enableFrameFilter`](#enableframefilter)
- [`setMaxFrameRate`](#setmaxframerate)

## enableSensorControl

Turn on (off) sensor control

Objective-C:

```objectivec
    [dce enableSensorControl:true];
    //To check the status of the DCE sensor control
    BOOL res= [dce enableSensorControl];
```

Swift:

```swift
    dce.enableSensorControl(true)
    //To check the status of the DCE sensor control
    let res = dce.enableSensorControl
```

## setSensorControlThreshold

This API is designed for developers to apply different sensor sensitivity settings on different devices. The default value is 50.

Objective-C:

```objectivec
    [dce setSensorControlThreshold:55];
```

Swift:

```swift
    dce.setSensorControlThreshold(55)
```

## enableFrameFilter

Turn on(off) DCE filter (recommended to be true).

Objective-C:

```objectivec
    [dce enableFrameFilter:true];
    //To check the status of the DCE frame filter
    BOOL res= [dce enableFrameFilter];
```

Swift:

```swift
    dce.enableFrameFilter(true)
    //To check the status of the DCE frame filter
    let res = dce.enableFrameFilter
```

## setMaxFrameRate

Set max frame rate.

Objective-C:

```objectivec
    [dce setMaxFrameRate:24];
```

Swift:

```swift
    dce.setMaxFrameRate(24)
```
