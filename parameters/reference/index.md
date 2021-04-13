---
layout: default-layout
title: Dynamsoft Camera Enhancer - Parameters reference
description: This is the documentation - Parameters reference page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, Parameters reference
needAutoGenerateSidebar: true
breadcrumbText: Java (Android), Objective-C (IOS)
---
# Dynamsoft Camera Enhancer - Parameters Reference

## Camera state
| Member (Java/Android) | Value | Description |
|-----------------------|-------|-------------|
| `CameraState.CAMERA_STATE_OFF` | 0 | Set camera off. |
| `CameraState.CAMERA_STATE_ON` | 1 | Set camera on. |

## Camera Position

| Member (Java/Android) | Value | Description |
|-----------------------|-------|-------------|
| `CameraPosition.CAMERA_POSITION_USER` | 0 | Use front camera. |
| `CameraPosition.CAMERA_POSITION_WORLD` | 1 | Use back camera. |

## Torch State

| Member (Java/Android) | Value | Description |
|-----------------------|-------|-------------|
| `TorchState.TORCH_STATE_OFF` | 0 | Turn off torch. |
| `TorchState.TORCH_STATE_ON` | 1 | Turn on torch. |
| `TorchState.TORCH_STATE_AUTO` | 2 | Auto turn on/off torch. |

## Resolution

| Member (Java/Android) | Value | Description |
|-----------------------|-------|-------------|
| `Resolution.RESOLUTION_AUTO` | 0 | Set resolution auto. |
| `Resolution.RESOLUTION_480P` | 1 | Set resolution at 480p. |
| `Resolution.RESOLUTION_720P` | 2 | Set resolution at 720p. |
| `Resolution.RESOLUTION_1080P` | 3 | Set resolution at 1080p. |
| `Resolution.RESOLUTION_2K` | 4 | Set resolution at 2k. |
| `Resolution.RESOLUTION_4K` | 5 | Set resolution at 4k. |

## HardwareUtil

| Member (Java/Android) | Value | Description |
|-----------------------|-------|-------------|
| `HardwareUtil.DEVICEINFO_UNKNOWN` | -1 | Device info can't be detected. |
| `HardwareUtil.DEVICE_LEVEL_HIGH` | 2 | Device level is detected to be high. |
| `HardwareUtil.DEVICE_LEVEL_MID` | 1 | Device level is detected to be medium. |
| `HardwareUtil.DEVICE_LEVEL_LOW` | 0 | Device level is detected to be low. |
| `HardwareUtil.DEVICE_LEVEL_UNKNOWN` | -1 | Device level can't be detected. |