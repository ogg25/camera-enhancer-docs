---
layout: default-layout
title: Dynamsoft Camera Enhancer - License initialization
description: This is the documentation - License initialization page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, License initialization
needAutoGenerateSidebar: true
breadcrumbText: License Initialization
---
# License initialization

This section covers the following topics:

- [How to set up a trial license.](#Set-up-trial-license)
- [How to set up a full license.](#Sep-up-full-license)

## Get a trial key

- If you are a new user, trial license will be available for 7 days since you download DCE.
- If your free key is expired, you can [request for a trial extension online]().

## Get full key license

[Purchase DCE in online shop](). After getting a full key license, you will receive a default generated Handshake code. What you have to do to set up your license is to:


### Set up local license

If you are not tending to use dynamic license online, you can directly set up your local license with your key. 

```Java
```

### Set up license from License Tracking Server

Since you have set up your `Handshake Code` and `Session Password`, you can use following code to set up your license from `LTS`:
```Java
CameraLTSConnectionParameters info = new CameraLTSConnectionParameters();
    mCamera.initLicenseFromLTS(info, new CameraLTSLicenseVerificationListener() {
        @Override
        public void LTSLicenseVerificationCallback(boolean b, Exception e) {
            if(!b && e != null){
                e.printStackTrace();
            }
        }
    });
```

