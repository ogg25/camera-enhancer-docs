---
layout: default-layout
title: Dynamsoft Camera Enhancer - Android API references - Zoom & Focus Setting
description: This is the documentation - Android API references - Zoom & Focus Setting page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Focus, Zoom, Android API Reference
needAutoGenerateSidebar: true
breadcrumbText: Android Zoom and Focus
---

# Android API Reference - Zoom & Focus Setting

- [`setAutoFocusPosition`](#setautofocusposition)
- [`setManualFocusPosition`](#setautofocusposition)
- [`setFocalLength`](#setfocallength)
- [`enableDCEAutoFocus`](#enabledceautofocus)
- [`getEnabledDCEAutoFocusStatus`](#enabledceautofocus)
- [`enableDefaultAutoFocus`](#enabledefaultautofocus)
- [`getEnabledDefaultAutoFocusStatus`](#enabledefaultautofocus)
- [`enableRegularAutoFocus`](#enableregularautofocus)
- [`getEnabledRegularAutoFocusStatus`](#enableregularautofocus)
- [`setRegularAutoFocusParam`](#setregularautofocusparam)
- [`enableAutoFocusOnSharpnessChange`](#enableautofocusonsharpnesschange)
- [`getEnabledAutoFocusOnSharpnessChangeStatus`](#enableautofocusonsharpnesschange)
- [`enableAutoZoom`](#enableautozoom)
- [`getEnabledAutoZoomStatus`](#enableautozoom)
- [`setZoomFactor`](#setzoomfactor)

## setAutoFocusPosition

Set the position that you want to autp focus at. This setting will replace the default focus value and always focus on the setted point.

```Java
    mCamera.setAutoFocusPosition(0.5,0.6);
```

## setManualFocusPosition

Set the manual focus position. This position only effect once when this API is called.

```Java
    mCamera.setManualFocusPosition(0.5,0.6);
```

## setFocalLength

Set the focal length (float). The range of focal length is from 0 to 10. The value doesn't means a distance but a precentage. If user set `setFocalLength(5);` it means the focal length will be 50% of the maxium focal length of the camera. Please note, If this API is called to set a focal length, the focal length will be fixed and all other auto focus mode will be disabled. To quit this fixed focal length mode, please set the focal length into -1.

To enter the fixed focal length mode:
```java
    mCamera.setFocalLength(8.5);
```
To quit:
```java
    mCamera.setFocalLength(-1);
```

## enableDCEAutoFocus

This API is designed to turn on DCE auto focus mode which is specially designed and different from the system default auto focus mode. DCE auto focus and the default auto focus can work together at the same time without any conflict. The above focus settings are also available for controlling system default auto focus.

To turn on DCE auto focus mode:
```java
    mCamera.enableDCEAutoFocus(true);
```
To get status (on/off) of DCE auto focus mode:
```java
    boolean x = mCamera.getEnabledDCEAutoFocusStatus();
```

## enableDefaultAutoFocus

This API is designed for controlling the system default auto focus. To turn off default auto focus mode:
```java
    mCamera.enableDefaultAutoFocus(false);
```
To get status (on/off) of Default auto focus mode:
```java
    boolean x = mCamera.getEnabledDefaultAutoFocusStatus();
```

## enableRegularAutoFocus

Regular auto focus is an advanced setting that enable camera to auto focus for every 3 seconds. It is contained in DCE auto focus. When DCE auto focus is enabled, regular auto focus is enable as well. To turn off regular auto focus mode:
```java 
    mCameraEnhancer.enableRegularAutoFocus(false);
```
To get status (on/off) of regular auto focus mode:
```java
    boolean x = mCamera.getEnabledRegularAutoFocusStatus();
```

## setregularautofocusparam

There are focus interval time and focus terminate time for users to set in regular auto focus mode. Please use `setregularautofocusparam` to make these settings.
```java
    // Set focus interval = 3000 and focus terminate time = 500.
    mCamera.setRegularAutoFocusParam(3000, 500);
``` 

## enableAutoFocusOnSharpnessChange

This API is another advanced setting that enable camera to auto focus when sharpness change is detected between contiguous frames. The same with regular auto focus, this focus mode is also enabled by default when DCE auto focus is enabled. To turn off camera auto focus when sharpness changes:
```java
    mCameraEnhancer.enableAutoFocusOnSharpnessChange(false);
```
To get the status (on/off) of this auto focus mode:
```java
    boolean x = mCamera.getEnabledAutoFocusOnSharpnessChangeStatus();
```

## enableAutoZoom

DCE auto zoom mode can be enabled if user is using DCE to enhance decode performance. The auto zoom mode is base on decode region predicted algorithm. In DCE auto zoom mode, If the lastest decoded frame is predicted to contain a barcode but fail on decoding, DCE will control the camera to zoom in to approach the barcode region.
To enable auto zoom mode:
```java
    mCamera.enableAutoZoom(true);
```
To check the status (on/off) of auto zoom mode:
```java
    boolean x = mCamera.getEnabledAutoZoomStatus();
```

## setZoomFactor

Set zoom factor (float).
```java
    mCamera.setZoomFactor(1.5);
```