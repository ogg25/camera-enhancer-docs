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

Turn on auto focus.
```java
    mCamera.enableAutoFocus(true);
```

### setAutoFocusAt
    
Set the position you want to auto focus at.
```java
    mCamera.setAutoFocusAt(int,int);
```
### setManualFocusAt

Set the position you want to manually focus at
```java
    mCamera.setManualFocusAt(int,int);
```

### setFocalLength

Set focal length (float).
```java
    try {
        mCamera.setFocalLength(float);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```

### enableRegularAutoFocus

Set auto focus interval
```java
    //Auto focus for every 3000ms. 
    mCameraEnhancer.enableRegularAutoFocus(true);
```

### enableAutoFocusOnSharpnessChange

Enable camera to focus when clarity changes
```java
    mCameraEnhancer.enableAutoFocusOnSharpnessChange(true);
```

### setAutoZoom

Turn on auto zoom.
```java
    mCamera.setAutoZoom(true);
```

### setZoomFactor

Set zoom factor (float).
```java
    try {
        mCamera.setZoomFactor(float);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```