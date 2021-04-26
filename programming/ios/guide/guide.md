---
layout: default-layout
title: Dynamsoft Camera Enhancer - Guide on Objective-C & Swift
description: This is the documentation - Guide on Objective-C & Swift page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Guide on Objective-C & Swift
needAutoGenerateSidebar: true
breadcrumbText: iOS Guide
---

# Guide on Objective-C & Swift

## Quick access

- [Installation](#installation)
- [License Initialization](#license-initialization)
- [Get start with DCE](#get-start)

## System Requirements

- Operating systems:
    - macOS 10.11 and above.
    - iOS 9.0 and above.
- Environment: Xcode 7.1 - 11.5 and above.
- Recommended: macOS 10.15.4+, Xcode 11.5+, iOS 11+

## Installation

1. <a href="https://download.dynamsoft.com/dce/dce-ios-1.0.zip?ver=latest" target="_blank">Download Dynamsoft Camera Enhancer</a> from Dynamsoft website to get `dce-android-{version-number}.zip`. Unzip the package and find DynamsoftCameraEnhancer.framework. 

2. Create a new Objective-C or Swift project.

3. Add DynamsoftCameraEnhancer.framework in your xcode project. 
(How to add framework on xcode)

4. Import Dynamsoft Camera Enhancer

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
    iDMLTSConnectionParameters* dcePara = [[iDMLTSConnectionParameters alloc] init];
    dcePara.organizationID = @"Your organizationID";
    dce = [[DynamsoftCameraEnhancer alloc] initLicenseFromLTS:dcePara view:dceview verificationDelegate:self];
```
Swift:
```Swift
    let lts = iDMLTSConnectionParameters()
    lts.organizationID = "Your organizationID"
    dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
```

If you don't have a full key license:

- 7 days trial license is available for new devices that have never setup Dynamsoft Camera Enhancer.
- To extend your trial license, please send "privateTrial" to trial@dynamsoft.com to get 30 days private trial key.

Or you can

- [Please contact us to purchase for full key license]({{site.contact-us}}).

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
    dceView = [DCECaptureView captureWithFrame:self.view.bounds];
    //Initialize license from LTS
    iDMLTSConnectionParameters* dcePara = [[iDMLTSConnectionParameters alloc] init];
    dcePara.organizationID = @"Your organizationID";
    dce = [[DynamsoftCameraEnhancer alloc] initLicenseFromLTS:dcePara view:dceview verificationDelegate:self];
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
        lts.organizationID = "Your organizationID"
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
    dceView = [DCECaptureView captureWithFrame:self.view.bounds];
    // License initialization
    iDMLTSConnectionParameters* dcePara = [[iDMLTSConnectionParameters alloc] init];
    dcePara.organizationID = @"Your organizationID";
    dce = [[DynamsoftCameraEnhancer alloc] initLicenseFromLTS:dcePara view:dceview verificationDelegate:self];
    //Camera & scan settings
    [dce setCameraDesiredState:CAMERA_STATE_ON];
    [dce startScanning];
    [dce setEnableFastMode:true];
    [dce setEnableFrameFilter:true];
    [dce setEnableAutoZoom:true];
    [dce setEnableDCEAutoFocus:true];
    [dce setIsEnable = false];
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
        lts.organizationID = "Your organizationID"
        dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
        
        //DCE recommended settings 
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.startScanning()
        dce.enableFastMode(true)
        dce.enableFrameFilter(true)
        dce.enableDCEAutoFocus(true)
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
    dceView = [DCECaptureView captureWithFrame:self.view.bounds];
    iDMLTSConnectionParameters* dcePara = [[iDMLTSConnectionParameters alloc] init];
    dcePara.organizationID = @"Your organizationID";
    dce = [[DynamsoftCameraEnhancer alloc] initLicenseFromLTS:dcePara view:dceview verificationDelegate:self];
    [dce setCameraDesiredState:DCEnhancerStateOn];
    [dce startScanning];
    //**********Start Fast mode*************
    [dce enableFastMode:true];
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
        lts.organizationID = "Your organizationID"
        dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.startScanning()
        //Turn on fast mode
        dce.enableFastMode(true)
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
    dceView = [DCECaptureView captureWithFrame:self.view.bounds];
    iDMLTSConnectionParameters* dcePara = [[iDMLTSConnectionParameters alloc] init];
    dcePara.organizationID = @"Your organizationID";
    dce = [[DynamsoftCameraEnhancer alloc] initLicenseFromLTS:dcePara view:dceview verificationDelegate:self];
    //**********Filter, Focus and Zoom settings*************
    //Turn on/off filter
    [dce enableFrameFilter:true];
    //Turn on/off auto zoom
    [dce enableAutoZoom];
    //Turn on/off auto focus
    [dce enableDCEAutoFocus:true];
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
        lts.organizationID = "Your organizationID"
        dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
        dce.setCameraDesiredState(.CAMERA_STATE_ON)
        dce.startScanning()
        //Turn on/off auto focus
        dce.enableDCEAutoFocus(true)
        //Turn on/off filter
        dce.enableFrameFilter(true)
        //Turn on/off auto zoom
        dce.enableAutoZoom = true
    }
}
```

Specially, for auto focus there are APIs `setAutoFocusPosition` and `setManualFocusPosition` designed for changing the default focus point. The value of this property is a CGPoint that determines the receiver's focus point of interest, if it has one. A value of (0,0) indicates that the camera should focus on the top left corner of the image, while a value of (1,1) indicates that it should focus on the bottom right. The default value is (0.5,0.5).

Objective-C
```objectivec
    [dce setAutoFocusPosition:CGPointMake(0.5, 0.5)];
    [dce setManualFocusPosition:CGPointMake(0.5, 0.5)];
```

Swift:
```Swift
    dce.setAutoFocusPosition(CGPoint(x: 0.5, y: 0.5))
    dce.setManualFocusPosition(CGPoint(x: 0.5, y: 0.5))
```

## Add DCE to your Dynamsoft Barcode Reader (DBR) project

For developers who are using Dynamsoft Barcode reader, there are new APIs in DBR 8.2.1 mobile edition to quick deploy camera enhancer in barcode reader project. For more information please read more in [DBR documentation - camera enhancer deployment]({{site.barcode-deploy-ios}}) section.