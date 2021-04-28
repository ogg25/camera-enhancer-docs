---
layout: default-layout
title: Dynamsoft Camera Enhancer - Objective-C & Swift API references - Zoom & Focus Setting
description: This is the documentation - Objective-C & Swift API references - Zoom & Focus Setting page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Objective-C & Swift API references, Zoom, Focus
needAutoGenerateSidebar: true
breadcrumbText: iOS Zoom and Focus
---

# iOS API Reference - Zoom & Focus Setting

- [`setAutoFocusPosition`](#setautofocusposition)
- [`setManualFocusPosition`](#setmanualfocusposition)
- [`setFocalLength`](#setfocallength)
- [`enableDCEAutoFocus`](#enabledceautofocus)
- [`enableDefaultAutoFocus`](#enabledefaultautofocus)
- [`enableRegularAutoFocus`](#enableregularautofocus)
- [`enableAutoFocusOnSharpnessChange`](#enableautofocusonsharpnesschange)
- [`enableAutoZoom`](#enableautozoom)
- [`setZoomFactor`](#setzoomfactor)

## setAutoFocusPosition

Set the position you want to auto focus at. This setting will replace the default focus value and always focus on the setted point.

Objective-C:

```objectivec
    [dce setAutoFocusPosition:CGPointMake(0.5, 0.5)];
```

Swift:

```Swift
    dce.setAutoFocusPosition(CGPoint(x: 0.5, y: 0.5))
```

## setManualFocusPosition

Set the position you want to manually focus at. This focus position effects only once each time this code is called.

Objective-C:

```objectivec
    [dce setManualFocusPosition:CGPointMake(0.5, 0.5)];
```

Swift:

```Swift
    dce.setManualFocusPosition(CGPoint(x: 0.5, y: 0.5))
```

## setFocalLength

Set focal length (float). The range of focal length is from 0 to 1. The value doesn't means a distance but a precentage. If user set `setFocalLength(0.5);` it means the focal length will be 50% of the maxium focal length of the camera. Please note, If this API is called to set a focal length, the focal length will be fixed and all other auto focus mode will be disabled. To quit this fixed focal length mode, please set the focal length into -1.

Objective-C:

```objectivec
    [dce setFocalLength:0.8];
```

Swift:

```Swift
    dce.setFocalLength = 0.8
```

## enableDCEAutoFocus

This API is designed to turn on DCE auto focus mode which is specially designed and different from the system default auto focus mode. DCE auto focus and the default auto focus can work together at the same time without any conflict. The above focus settings are also available for controlling system default auto focus. To turn on DCE auto focus mode:

Objective-C:

```objectivec
    [dce enableDCEAutoFocus:true];
    //To check the status of DCE auto focus.
    bool res = [dce enableDCEAutoFocus];
```

Swift:

```Swift
    dce.enableDCEAutoFocus = true
    //To check the status of DCE auto focus.
    let res = dce.enableDCEAutoFocus
```

## enableDefaultAutoFocus

This API is designed for controlling the system default auto focus. To turn off default auto focus mode:

Objective-C:

```objectivec
    [dce enableDefaultAutoFocus:false];
    //To check the status of system default auto focus.
    bool res = [dce enableDefaultAutoFocus];
```

Swift:

```Swift
    dce.enableDefaultAutoFocus = false
    //To check the status of system default auto focus.
    let res = dce.enableDefaultAutoFocus
```

## enableRegularAutoFocus

Regular auto focus is an advanced setting that enable camera to auto focus for every 3 seconds. It is contained in DCE auto focus. When DCE auto focus is enabled, regular auto focus is enable as well. To turn off regular auto focus mode:

Objective-C:

```objectivec
    [dce enableRegularAutoFocus:false];
    //To check the status of DCE auto focus.
    bool res = [dce enableRegularAutoFocus];
```

Swift:

```Swift
    dce.enableRegularAutoFocus = false
    //To check the status of DCE regular auto focus.
    let res = dce.enableRegularAutoFocus
```

## enableAutoFocusOnSharpnessChange

This API is another advanced setting that enable camera to auto focus when sharpness change is detected between contiguous frames. The same with regular auto focus, this focus mode is also enabled by default when DCE auto focus is enabled. To turn off camera auto focus when sharpness changes:

Objective-C:

```objectivec
    [dce enableAutoFocusOnSharpnessChange:false];
    //To check the status of DCE sharpness focus.
    bool res = [dce enableAutoFocusOnSharpnessChange];
```

Swift:

```Swift
    dce.enableAutoFocusOnSharpnessChange = false
    //To check the status of DCE sharpness focus.
    let res = dce.enableAutoFocusOnSharpnessChange
```

## enableAutoZoom

DCE auto zoom mode can be enabled if user is using DCE to enhance decode performance. The auto zoom mode is base on decode region predicted algorithm. In DCE auto zoom mode, If the lastest decoded frame is predicted to contain a barcode but fail on decoding, DCE will control the camera to zoom in to approach the barcode region. To enable auto zoom mode:

Objective-C:

```objectivec
    [dce enableAutoZoom:true];
    //To check the status of DCE auto zoom.
    bool res = [dce enableAutoZoom];
```

Swift:

```Swift
    dce.enableAutoZoom = true
    //To check the status of DCE auto zoom.
    let res = dce.enableAutoZoom
```

## setZoomFactor

Set zoom factor (float).

Objective-C:

```objectivec
    [dce setZoomFactor:1.5];
```

Swift:

```Swift
    dce.setZoomFactor = 1.5
```
