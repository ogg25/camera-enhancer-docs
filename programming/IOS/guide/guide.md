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
    - [Quick Setup](#Quick-Settings-for-DCE)
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

To setup DCE license by License Tracking Server

Objective-C:
```objectivec
    DynamsoftCameraEnhancer *dce;
    iDMLTSConnectionParameters* lts = [[iDMLTSConnectionParameters alloc] init];
    lts.handshakeCode = @"Your handshakeCode";
    lts.sessionPassword = @"******";
    dce = [[DynamsoftCameraEnhancer alloc] initLicenseFromLTS:lts verificationDelegate:self];
    - (void)LTSLicenseVerificationCallback:(bool)isSuccess error:(NSError * _Nullable)error
    {
            //TODO add your code for license verification
    }
```
Swift:
```Swift
    let lts = iCameraLTSConnectionParameters()
    lts.handshakeCode = "Your handshakeCode"
    lts.mainServerURL = "https://mtplres.dynamsoft.com"
    dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
```

If you don't have a full key license:

- 7 days trial license is available for new devices that have never setup Dynamsoft Camera Enhancer.
- To extend your trial license, please send "Private trial" to trial@dynamsoft.com to get 30 days private trial key.

Or you can

- [Learn more about full key license]()

## Get Start

### Create a Camera Module

In this section you will be guide on using Dynamsoft Camera Enhancer to create a simple camera app with video frame filter function.

If you have completed the installation of DCE, you can add following code to your viewController to set up your camera module.

Objective-C
```objectivec
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>

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
    var dce:DynamsoftCameraEnhancer! = nil
    var dceView:DCECaptureView! = nil
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.isEnable = true
    }
    func configurationDCE() {
        dceDate = NSDate()
        dceView = DCECaptureView.init(view: self.view.bounds)
        dceView.addOverlay(color, fill: color)
        self.view.insertSubview(dceView, belowSubview: displayView)
        //Setup license
        let lts = iCameraLTSConnectionParameters()
        lts.handshakeCode = "100014901-8002module-test"
        lts.mainServerURL = "https://mtplres.dynamsoft.com"
        dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
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

    dce.isEnable = true;
}
```

Swift:
```Swift
import DynamsoftCameraEnhancer

class ViewController: UIViewController {
    var dce:DynamsoftCameraEnhancer! = nil
    var dceView:DCECaptureView! = nil
    override func viewDidLoad() {
        super.viewDidLoad()
        
        //Turn on camera
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.isEnable = true
    }
    func configurationDCE() {
        dceDate = NSDate()
        dceView = DCECaptureView.init(view: self.view.bounds)
        dceView.addOverlay(color, fill: color)
        self.view.insertSubview(dceView, belowSubview: displayView)
        
        //Setup license
        let lts = iCameraLTSConnectionParameters()
        lts.handshakeCode = "100014901-8002module-test"
        lts.mainServerURL = "https://mtplres.dynamsoft.com"
        dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
        
        //DCE recommended settings 
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.startScanning()
        dce.setFastMode(true)
        dce.setUseFrameFilter(true)
        dce.setForceAutoFocus(true)
        dce.enableAutoZoom = true
    }
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
import DynamsoftCameraEnhancer

class ViewController: UIViewController {
    var dce:DynamsoftCameraEnhancer! = nil
    var dceView:DCECaptureView! = nil
    override func viewDidLoad() {
        super.viewDidLoad()
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.isEnable = true
    }
    func configurationDCE() {
        dceDate = NSDate()
        dceView = DCECaptureView.init(view: self.view.bounds)
        dceView.addOverlay(color, fill: color)
        self.view.insertSubview(dceView, belowSubview: displayView)
        let lts = iCameraLTSConnectionParameters()
        lts.handshakeCode = "100014901-8002module-test"
        lts.mainServerURL = "https://mtplres.dynamsoft.com"
        dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.startScanning()
        //Turn on fast mode
        dce.setFastMode(true)
    }
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
import DynamsoftCameraEnhancer

class ViewController: UIViewController {
    var dce:DynamsoftCameraEnhancer! = nil
    var dceView:DCECaptureView! = nil
    override func viewDidLoad() {
        super.viewDidLoad()
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.isEnable = true
    }
    func configurationDCE() {
        dceDate = NSDate()
        dceView = DCECaptureView.init(view: self.view.bounds)
        dceView.addOverlay(color, fill: color)
        self.view.insertSubview(dceView, belowSubview: displayView)
        let lts = iCameraLTSConnectionParameters()
        lts.handshakeCode = "100014901-8002module-test"
        lts.mainServerURL = "https://mtplres.dynamsoft.com"
        dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.startScanning()
        //Turn on/off auto focus
        dce.setForceAutoFocus(true)
        //Turn on/off filter
        dce.setUseFrameFilter(true)
        //Turn on/off auto zoom
        dce.enableAutoZoom = true
    }
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