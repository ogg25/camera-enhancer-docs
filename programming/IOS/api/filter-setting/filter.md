---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references
description: This is the documentation - Objective-C & Swift API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references
needAutoGenerateSidebar: true
breadcrumbText: Java
---

# Dynamsoft Camera Enhancer - Objective-C & Swift API references

## Filter Setting

- [`sensorControl`](#sensorControl)
- [`setUseFrameFilter`](#setUseFrameFilter)
- [`setMaxFrameRate`](#setMaxFrameRate)

### sensorControl
    
Turn on(off) sensor control

Objective-C
```objectivec
    [dce sensorControl:3];
```

Swift
```Swift
    dce.sensorControl(3);
```

### setUseFrameFilter

Turn on(off) DCE filter (recommended to be true).

Objective-C
```objectivec
    [dce setUseFrameFilter:true];
```

Swift
```Swift
    dce.setUseFrameFilter(true);
```

### setMaxFrameRate

Set max frame rate.

Objective-C
```objectivec
    [dce setMaxFrameRate:24];
```

Swift
```Swift
    dce.setMaxFrameRate(24);
```