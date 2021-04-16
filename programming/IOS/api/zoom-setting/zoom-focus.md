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

- [`enableAutoFocus`](#enableAutoFocus)
- [`setAutoFocusAt`](#setAutoFocusAt)
- [`setManualFocusAt`](#setManualFocusAt)
- [`setForcedFocusLength`](#setForcedFocusLength)
- [`enableRegularAutoFocus`](#enableRegularAutoFocus)
- [`enableAutoFocusOnSharpnessChange`](#enableAutoFocusOnSharpnessChange)
- [`enableAutoZoom`](#enableAutoZoom)
- [`setZoomFactor`](#setZoomFactor)

### enableAutoFocus

Turn on force auto focus.

Objective-C
```objectivec
    [dce enableAutoFocus:true];
```

Swift
```Swift
    dce.enableAutoFocus(true);
```

### setAutoFocusAt
    
Set the position you want to auto focus at.

Objective-C
```objectivec
    [dce setAutoFocusAt:CGPointMake(0.5, 0.5)];
```
Swift
```Swift
    dce.setAutoFocusAt(CGPoint(x: 0.5, y: 0.5));
```

### setManualFocusAt

Set the position you want to manually focus at

Objective-C
```objectivec
    [dce setManualFocusAt:CGPointMake(0.5, 0.5)];
```

Swift
```Swift
    dce.setManualFocusAt(CGPoint(x: 0.5, y: 0.5));
```

### setFocalLength

Set focal length (float).

Objective-C
```objectivec
    [dce setFocalLength:2];
```

Swift
```Swift
    dce.setFocalLength(2);
```

### enableRegularAutoFocus

Set auto focus interval
Objective-C
```objectivec
```

Swift
```Swift
```

### enableAutoFocusOnSharpnessChange

Enable camera to focus when clarity changes
Objective-C
```objectivec
```

Swift
```Swift
```

### enableAutoZoom

Turn on auto zoom.

Objective-C
```objectivec
    [dce enableAutoZoom];
```

Swift
```Swift
    dce.enableAutoZoom = true;
```

### setZoomFactor

Set zoom factor (float).

Objective-C
```objectivec
    [dce setZoomFactor:2];
```

Swift
```Swift
    dce.setZoomFactor(2);
```