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

- [`setAutoFocusAt`](#setAutoFocusAt)
- [`manualFocusOnce`](#manualFocusOnce)
- [`setForcedFocusLength`](#setForcedFocusLength)
- [`setForceAutoFocus`](#setForceAutoFocus)
- [`setAutoZoom`](#setAutoZoom)
- [`setZoomFactor`](#setZoomFactor)

### setAutoFocusAt
    
Set the position you want to auto focus at.
```java
    mCamera.setAutoFocusAt(int,int);
```
### manualFocusOnce
Set the position you want to manually focus at
```java
    mCamera.manualFocusOnce(int,int);
```
### setForcedFocusLength
Set focal length (float).
```java
    try {
        mCamera.setForcedFocusLength(float);
    } catch (CameraEnhancerException e) {
        e.printStackTrace();
    }
```
### setForceAutoFocus
Turn on force auto focus.
```java
    mCamera.setForceAutoFocus(true);
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