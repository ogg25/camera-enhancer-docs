---
layout: default-layout
title: Dynamsoft Camera Enhancer - License initialization
description: This is the documentation - License initialization page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, License initialization
needAutoGenerateSidebar: true
breadcrumbText: License Initialization
---
# License initialization

## Get a trial key

- 7 days public trial key is available for every new device that have never activated Dynamsoft Camera Enhancer.
- If your free key is expired, please email trial@dynamsoft.com and include "privateTrial" in the title to get 30 days extension.

## Get full key license

- [Click here to view DCE purchase page]().

## Set up license from License Tracking Server

Since you have set up your, you can use following code to set up your license from `LTS`:

For Android users:
 
Android sample
```Java
    DMLTSConnectionParameters info = new DMLTSConnectionParameters();
    info.organizationID = "******";
    mCamera.initLicenseFromLTS(info, new CameraLTSLicenseVerificationListener() {
        @Override
        public void LTSLicenseVerificationCallback(boolean b, Exception e) {
            if(!b && e != null){
                e.printStackTrace();
            }
        }
    });
```

For iOS users: 

Swift sample
```Swift
    let lts = iDMLTSConnectionParameters()
    lts.organizationID = "200001"
    dce = DynamsoftCameraEnhancer.init(licenseFromLTS: lts, view: dceView, verificationDelegate: self)
```