---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references
description: This is the documentation - Android API references page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Android API references
needAutoGenerateSidebar: true
breadcrumbText: Java
---

# Dynamsoft Camera Enhancer - Android API references

## Camera settings - Zoom & Focus Setting

- [`setAutoFocusPoint`](#setAutoFocusPoint)
- [`manualFocusOnce`](#manualFocusOnce)
- [`setForcedFocusLength`](#setForcedFocusLength)
- [`setForceAutoFocus`](#setForceAutoFocus)
- [`enableAutoZoom`](#enableAutoZoom)
- [`setZoomFactor`](#setZoomFactor)

### setAutoFocusPoint
    
Set the position you want to auto focus at.
```objectivec
    [dce setAutoFocusPoint:CGPointMake(0.5, 0.5)];
```
```Swift
    dce.setAutoFocus(CGPoint(x: 0.5, y: 0.5));
```

### manualFocusOnce

Set the position you want to manually focus at
```objectivec
    [dce manualFocusOnce:CGPointMake(0.5, 0.5)];
```
```Swift
    dce.manualFocusOnce(CGPoint(x: 0.5, y: 0.5));
```

### setForcedFocusLength

Set focal length (float).
```objectivec
    [dce setForcedFocusLength:2];
```
```Swift
    dce.setForcedFocusLength(2);
```

### setForceAutoFocus

Turn on force auto focus.
```objectivec
    [dce setForceAutoFocus:true];
```
```Swift
    dce.setForceAutoFocus(true);
```

### enableAutoZoom

Turn on auto zoom.
```objectivec
    [dce enableAutoZoom];
```
```Swift
    dce.enableAutoZoom = true;
```

### setZoomFactor

Set zoom factor (float).
```objectivec
    [dce setZoomFactor:2];
```
```Swift
    dce.setZoomFactor(2);
```