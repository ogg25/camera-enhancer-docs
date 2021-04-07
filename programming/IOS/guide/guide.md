---
layout: default-layout
title: Dynamsoft Camera Enhancer - Guide on Objective-C & Swift
description: This is the documentation - Guide on Objective-C & Swift page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Guide on Objective-C & Swift
needAutoGenerateSidebar: true
breadcrumbText: Objective-C & Swift
---

# Dynamsoft Camera Enhancer - Guide on Objective-C & Swift

## Quick access

- [Installation](#Installation)
- [Get start with DCE](#Get-Start)
- [Add DCE to your project](#Add-DCE-to-your-project)

## System Requirements

- Operating systems:
    - macOS 10.11 and above.
    - iOS 9.0 and above.
- Environment: Xcode 7.1 - 11.5 and above.
- Recommended: macOS 10.15.4+, Xcode 11.5+, iOS 11+

## Installation

1. [Download Dynamsoft Camera Enhancer]() from Dynamsoft website to get `dce-android-{version-number}.zip`. Unzip the package and find DynamsoftCameraEnhancer.framework. 

2. Add DynamsoftCameraEnhancer.framework in your xcode project. 
(How to add framework on xcode)

3. Import Dynamsoft Camera Enhancer

Objective-C:
```objectivec
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
```
Swift:
```Swift
import DynamsoftCameraEnhancer
```

## License Initialization

## Get Start

### Create a Camera Module

In this section you will be guide on using Dynamsoft Camera Enhancer to create a simple camera app with video frame filter function.

If you have completed the installation of DCE, you can add following code to your viewController to set up your camera module.

Objective-C
```objectivec
@interface ViewController ()
@end
@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view.
    DCECaptureView* view = [[DCECaptureView alloc] initWithView:self.view.bounds];
    [view addTorch];
    DynamsoftCameraEnhancer* dce = [[DynamsoftCameraEnhancer alloc] initWithView:view];
    [dce setCameraDesiredState:DCEnhancerStateOn];
}
```
Swift:
```Swift
import DynamsoftCameraEnhancer
class ViewController: UIViewController {
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
        do {
            let dce = DynamsoftCameraEnhancer.init(view:);
            dce.setCameraDesiredState(CameraState.on);
            dce.startScanning();
        }
    }
}
```

### Quick Settings for DCE

1. DCE Setting templete

The following templates are strongly recommended to be applicated in your first attempt on DCE. These templates will be friendly to the majority of IOS devices. By using and optimizing on this template, you will quickly be familiar with DCE.

Objective-C:
```objectivec
@interface ViewController ()
@end
@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view.
    DCECaptureView* view = [[DCECaptureView alloc] initWithView:self.view.bounds];
    [view addTorch];
    DynamsoftCameraEnhancer* dce = [[DynamsoftCameraEnhancer alloc] initWithView:view];
    [dce setCameraDesiredState:DCEnhancerStateOn];
    [dce startScanning];
    [dce setFastMode:true];
    [dce setUseFrameFilter:true];
    [dce enableAutoZoom];
    [dce setForceAutoFocus:true];

    dce.isEnable = false;
}
```

Swift:
```Swift
    do {
        let dce = DynamsoftCameraEnhancer.init(view:);
        dce.setCameraDesiredState(CameraState.on);
        dce.startScanning();
        dce.setFastMode(true);
        dce.setForceAutoFocus(true);
        dce.setUseFrameFilter(true);
        dce.enableAutoZoom = true;
    }
```
2. Fast mode setting

DCE fast mode is specially designed for accelerating on single barcode decoding. This mode will reduce the time consumption on single barcode decoding by 50%. Fast mode is strongly recommended to be enabled on single barcode decoding. To turn on Fast mode, you can use `setFastMode` to make the setting:

Objective-C
```objectivec
- (void)viewDidLoad {
    [super viewDidLoad];
    //Initialize DCE and turn on the camera
    DCECaptureView* view = [[DCECaptureView alloc] initWithView:self.view.bounds];
    [view addTorch];
    DynamsoftCameraEnhancer* dce = [[DynamsoftCameraEnhancer alloc] initWithView:view];
    [dce setCameraDesiredState:DCEnhancerStateOn];
    [dce startScanning];
    //**********Start Fast mode*************
    [dce setFastMode:true];
}
```

Swift:
```Swift
    do {
        let dce = DynamsoftCameraEnhancer.init(view:);
        dce.setCameraDesiredState(CameraState.on);
        dce.startScanning();
        dce.setFastMode(true);
    }
```

3. Filter, Focus and Zoom setting

The following code is guidline on how to setup frame filter, auto zoom and auto focus in DCE.

Objective-C
```objectivec
- (void)viewDidLoad {
    [super viewDidLoad];
    //Initialize DCE
    DCECaptureView* view = [[DCECaptureView alloc] initWithView:self.view.bounds];
    [view addTorch];
    DynamsoftCameraEnhancer* dce = [[DynamsoftCameraEnhancer alloc] initWithView:view];
    //**********Filter, Focus and Zoom settings*************
    //Turn on/off filter
    [dce setUseFrameFilter:true];
    //Turn on/off auto zoom
    [dce enableAutoZoom];
    //Turn on/off auto focus
    [dce setForceAutoFocus:true];
}
```

Swift:
```Swift
    do {
        let dce = DynamsoftCameraEnhancer.init(view:)
        dce.setCameraDesiredState(CameraState.on)
        dce.startScanning()
        //Turn on/off auto focus
        dce.setForceAutoFocus(true)
        //Turn on/off filter
        dce.setUseFrameFilter(true)
        //Turn on/off auto zoom
        dce.enableAutoZoom = true
    }
```

Specially, for auto focus there are APIs `setAutoFocusPoint` and `manualFocusOnce` designed for changing the default focus point. The value of this property is a CGPoint that determines the receiver's focus point of interest, if it has one. A value of (0,0) indicates that the camera should focus on the top left corner of the image, while a value of (1,1) indicates that it should focus on the bottom right. The default value is (0.5,0.5).

Objective-C
```objectivec
    [dce setAutoFocusPoint:CGPointMake(0.5, 0.5)];
    [dce manualFocusOnce:CGPointMake(0.5, 0.5)];
```

Swift:
```Swift
    dce.setAutoFocus(CGPoint(x: 0.5, y: 0.5))
    dce.manualFocusOnce(CGPoint(x: 0.5, y: 0.5))
```