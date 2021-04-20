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
| Java(Android) | class EnumDMChargeWay |

### Members

| Member (Java/Android) | Value | Description |
|-----------------------|-------|-------------|
| `DM_CW_AUTO` | 0 | The charge way automatically determined by the license server. |
| `DM_CW_DEVICE_COUNT` | 1 | Charges by the count of devices. |
| `DM_CW_CONCURRENT_DEVICE_COUNT` | 3 | Charges by the count of concurrent devices. |
| `DM_CW_APP_DOMAIN_COUNT` | 6 | Charges by the count of app domains. |
| `DM_CW_ACTIVE_DEVICE_COUNT` | 8 | Charges by the count of active devices. |

## DCE Error Code

### Declarations

| Language | Declaration |
|----------|-------------|
| Java(Android) | class EnumDCEErrorCode |

### Members

| Member (Java/Android) | Value | Description |
|-----------------------|-------|-------------|
| `DCE_OK` | 0 | Successful. |
| `DCE_LICENSE_INVALID` | -10001 | The licence is invalid. |
| `DCE_LICENSE_EXPIRED` | -10002 | The licence has expired. |
| `DCE_NOT_EXIST_CAMERA_MODULE` | -10003 | Camera module does not exists. |
| `DCE_NOT_FOUND_FILE` | -10004 | File is not found. |
| `DCE_FILE_FORMAT_ERROR` | -10004 | File format error. |
| `DCE_LICENSEKEY_NOT_MATCHED` | -10043 | The license key does not match the license content. |
| `DM_NO_LICENSE` | -20000 | There is no license specified. |
| `DM_HANDSHAKE_CODE_INVALID` | -20001 | Handshake code is invalid. |
| `DM_LICENSE_BUFFER_FAILED` | -20002 | Failed to read or write license buffer. |
| `DM_LICENSE_SYNC_FAILED` | -20003 | Failed to synchronize license info with license tracking server. |
| `DM_DEVICE_NOT_MATCH` | -20004 | Device does not match with license buffer. |
| `DM_BIND_DEVICE_FAILED` | -20005 | Failed to bind device. |
| `DM_LICENSE_INTERFACE_CONFLICT` | -20006 | interface InitLicenseFromLTS can not be used together with other license initiation interfaces. |
| `DM_LICENSE_CLIENT_DLL_MISSING` | -20007 | The license client dll is missing. |
| `DM_INSTANCE_COUNT_OVER_LIMITED` | -20008 | The number of instances used has exceeded the limit. |
| `DM_LICENSE_INIT_SEQUENCE_FAILED` | -20009 | Interface InitLicenseFromLTS has to be called before creating any SDK objects. |
| `DM_TRIAL_LICENSE` | -20010 | Using a trial license. |
| `DM_FAILED_TO_REACH_LTS` | -20200 | Fail to connect to license tracking server. |

## Camera DMUUID Generation Method

### Declarations

| Language | Declaration |
|----------|-------------|
| Java(Android) | class EnumCameraDMUUIDGenerationMethod |

### Members

| Member (Java/Android) | Value | Description |
|-----------------------|-------|-------------|
| `DM_UUIDGM_RANDOM` | 1 | Generates UUID with random values. |
| `DM_UUIDGM_HARDWARE` | 2 | Generates UUID based on hardware info. |