---
layout: default-layout
title: Dynamsoft Camera Enhancer - Enumerations
description: This is the documentation - Enumerations page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Enumerations
needAutoGenerateSidebar: true
breadcrumbText: Enumerations
---
# Enumerations

## DM_ChargeWay

### Declarations

| Language | Declaration |
|----------|-------------|
| Java(Android) | `class EnumDMChargeWay` |
| Objective-C & Swift | `enum EnumDMChargeWay` |

### Members

| Member (Android) | Member (iOS) | Value | Description |
|------------------|--------------|-------|-------------|
| `DM_CW_AUTO` | `EnumDMChargeWayAuto` | 0 | The charge way is automatically determined by the license server. |
| `DM_CW_DEVICE_COUNT` | `EnumDMChargeWayDeviceCount` | 1 | Charges by the count of devices. |
| `DM_CW_CONCURRENT_DEVICE_COUNT` | `EnumDMChargeWayConcurrentDeviceCount` | 3 | Charges by the count of concurrent devices. |
| `DM_CW_APP_DOMAIN_COUNT` | `EnumDMChargeWayAppDomainCount` | 6 | Charges by the count of app domains. |
| `DM_CW_ACTIVE_DEVICE_COUNT` | `EnumDMChargeWayActiveDeviceCount` | 8 | Charges by the count of active devices. |

&nbsp;

## Camera DMUUID Generation Method

### Declarations

| Language | Declaration |
|----------|-------------|
| Java(Android) | `class EnumCameraDMUUIDGenerationMethod` |
| Objective-C & Swift | `enum EnumCameraDMUUIDGenerationMethod` |

### Members

| Member (Android) | Member (iOS) | Value | Description |
|------------------|--------------|-------|-------------|
| `DM_UUIDGM_RANDOM` | `EnumDMUUIDGenerationMethodRandom` | 1 | Generates UUID with random values. |
| `DM_UUIDGM_HARDWARE` | `EnumDMUUIDGenerationMethodHardware` | 2 | Generates UUID based on hardware info. |

## DCE Error Code

DCE error common to all programming languages.

### Error code 0

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DCE_OK` | `EnumCameraErrorCode_OK`  | 0 | Successful. |

### Error code -10001

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DCE_LICENSE_INVALID` | `EnumCameraErrorCode_LICENSE_INVALID` | -10001 | The licence is invalid. |

### Error code -10002

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DCE_LICENSE_EXPIRED` | `EnumCameraErrorCode_LICENSE_EXPIRED` | -10002 | The licence has expired. |

### Error code -10003

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DCE_NOT_EXIST_CAMERA_MODULE` | `EnumCameraErrorCode_NOT_EXIST_CAMERA_MODULE` | -10003 | Camera module does not exist. |

### Error code -10004

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DCE_NOT_FOUND_FILE` | `EnumCameraErrorCode_NOT_FOUND_FILE` | -10004 | File is not found. |

### Error code -10005

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DCE_FILE_FORMAT_ERROR` | `EnumCameraErrorCode_FILE_FORMAT_ERROR` | -10005 | File format error. |

### Error code -10043

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DCE_LICENSEKEY_NOT_MATCHED` | iOS edition don't have error -10043 | -10043 | The license key does not match the license content. |

### Error code -10044

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| Android edition don't have error -10044 | `EnumCameraErrorCode_Requested_Failed` | -10044 | The license key does not match the license content. |

### Error code -20000

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_NO_LICENSE` | `EnumCameraErrorCode_NO_LICENSE` | -20000 | There is no license specified. |

### Error code -20001

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_HANDSHAKE_CODE_INVALID` | `EnumCameraErrorCode_HANDSHAKE_CODE_INVALID` | -20001 | Handshake code is invalid. |

### Error code -20002

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_LICENSE_BUFFER_FAILED` | `EnumCameraErrorCode_LICENSE_BUFFER_FAILED` | -20002 | Failed to read or write license buffer. |

### Error code -20003

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_LICENSE_SYNC_FAILED` | `EnumCameraErrorCode_LICENSE_SYNC_FAILED` | -20003 | Failed to synchronize license info with license tracking server. |

### Error code -20004

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_DEVICE_NOT_MATCH` | `EnumCameraErrorCode_DEVICE_NOT_MATCH` | -20004 | Device does not match with license buffer. |

### Error code -20005

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_BIND_DEVICE_FAILED` | `EnumCameraErrorCode_BIND_DEVICE_FAILED` | -20005 | Failed to bind device. |

### Error code -20006

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_LICENSE_INTERFACE_CONFLICT` | `EnumCameraErrorCode_LICENSE_INTERFACE_CONFLICT` | -20006 | Interface InitLicenseFromLTS can not be used together with other license initiation interfaces. |

### Error code -20007

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_LICENSE_CLIENT_DLL_MISSING` | `EnumCameraErrorCode_LICENSE_CLIENT_DLL_MISSING` | -20007 | The license client dll is missing. |

### Error code -20008

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_INSTANCE_COUNT_OVER_LIMITED` | `EnumCameraErrorCode_INSTANCE_COUNT_OVER_LIMITED` | -20008 | The number of instances used has exceeded the limit. |

### Error code -20009

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_LICENSE_INIT_SEQUENCE_FAILED` | `EnumCameraErrorCode_LICENSE_INIT_SEQUENCE_FAILED` | -20009 | Interface InitLicenseFromLTS has to be called before creating any SDK objects. |

### Error code -20010

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_TRIAL_LICENSE` | `EnumCameraErrorCode_TRIAL_LICENSE` | -20010 | Using a trial license. |

### Error code -20200

| Error Code (Android) | Error Code (iOS) | Value | Description |
|----------------------|------------------|-------|-------------|
| `DM_FAILED_TO_REACH_LTS` | `EnumCameraErrorCode_FAILED_TO_REACH_LTS` | -20200 | Fail to connect to license tracking server. |
