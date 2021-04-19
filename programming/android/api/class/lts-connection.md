---
layout: default-layout
title: Dynamsoft Camera Enhancer - CameraLTSConnectionParameters Class
description: This is the documentation - CameraLTSConnectionParameters Class page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, CameraLTSConnectionParameters Class
needAutoGenerateSidebar: true
breadcrumbText: Java
---

# CameraLTSConnectionParameters

Defines a struct to configure the parameters to connect to license tracking server.

## Method

| Name | Type |
|------|------|
| [`mainServerURL`]() | String |
| [`standbyServerURL`]() | String |
| [`handshakeCode`]() | String |
| [`organizationID`]() | String |
| [`sessionPassword`]() | String |
| [`uuidGenerationMethod`]() | int |
| [`maxBufferDays`]() | int |
| [`limitedLicenseModules`]() | list |
| [`chargeWay`]() | int |

### mainServerURL

The URL of the license tracking server.

```java
String com.dynamsoft.dce.CameraLTSConnectionParameters.mainServerURL
```

- **Value range**   
    Any string value   
      
- **Default value**   
    null

- **Remarks**   
    If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to null (default value), it will connect to Dynamsoft's license tracking servers for online verification.   


### standbyServerURL

The URL of the standby license tracking server.

```java
String com.dynamsoft.dce.CameraLTSConnectionParameters.standbyServerURL
```

- **Value range**   
    Any string value   
      
- **Default value**   
    null

- **Remarks**   
    If you choose "Dynamsoft-hosting", then no need to change the value of MainServerURL and StandbyServerURL. When both are set to null (default value), it will connect to Dynamsoft's license tracking servers for online verification.   

### handshakeCode

The handshake code.

```java
String com.dynamsoft.dce.CameraLTSConnectionParameters.handshakeCode
```

- **Value range**   
    Any string value   
      
- **Default value**   
    null

### organizationID

The organization ID

```java
String com.dynamsoft.dce.CameraLTSConnectionParameters.organizationID
```
- **Value range**   
    Any string value   
      
- **Default value**   
    null
    
### sessionPassword

The session password of the handshake code set in license tracking server.

```java
String com.dynamsoft.dce.CameraLTSConnectionParameters.sessionPassword
```

- **Value range**   
    Any string value   
      
- **Default value**   
    null


### uuidGenerationMethod

Sets the method to generate UUID.

```java
int com.dynamsoft.dce.CameraLTSConnectionParameters.uuidGenerationMethod
```

- **Value range**   
    Any one of the [`EnumDMUUIDGenerationMethod`]({{ site.enumerations }}other-enums.html#dm_uuidgenerationmethod) Enumeration items.   
      
- **Default value**   
    DM_UUIDGM_RANDOM   
    
- **See also**  
    [`EnumDMUUIDGenerationMethod`]({{ site.enumerations }}other-enums.html#dm_uuidgenerationmethod)    

### maxBufferDays

Sets the max days to buffer the license info.

```java
int com.dynamsoft.dce.CameraLTSConnectionParameters.maxBufferDays
```

- **Value range**   
    [7,0x7fffffff]  
      
- **Default value**   
    7   


### limitedLicenseModules

Sets the license modules to use.

```java
List<Integer> com.dynamsoft.dce.CameraLTSConnectionParameters.limitedLicenseModules
```

- **Value range**   
    A list of the [`EnumDMLicenseModule`]({{ site.enumerations }}other-enums.html#dm_licensemodule) Enumeration items.   
      
- **Default value**   
    null   
    
- **See also**  
    [`EnumDMLicenseModule`]({{ site.enumerations }}other-enums.html#dm_licensemodule)    

### chargeWay

Sets the charge way.

```java
int com.dynamsoft.dce.CameraLTSConnectionParameters.chargeWay
```

- **Value range**   
    Any one of the [`EnumDMChargeWay`]({{ site.enumerations }}other-enums.html#dm_chargeWay) Enumeration items.   
      
- **Default value**   
    DM_CW_AUTO   
    
- **See also**  
    [`EnumDMChargeWay`]({{ site.enumerations }}other-enums.html#dm_chargeWay)