---
layout: default-layout
title: Dynamsoft Camera Enhancer - Introduction
description: This is the documentation - introduction page of Dynamsoft Camera Enhancer.
keywords:  Camera Enhancer, introduction
needAutoGenerateSidebar: true
breadcrumbText: Introduction
---

# Introductions

## Overview of Dynamsoft Camera Enhancer

Dynamsoft Camera Enhancer (DCE) is an SDK specifically designed for improving video frame decoding. Before video frames are transferred for decoding, DCE will do a series of preprocessing includes camera control and frame filter. This step can largely reduce the rate of misreading. You can start your decode program development with DCE, and also you can import the DCE algorithm in your developed app to improve its performance.

## Main features

1. Autofocus

    If the device's default autofocus is not sensitive enough, DCE can provide a specially designed autofocus mode that can largely improve camera focus efficiency. Further, it also enables users to make personalized focus settings to reach various requirements.

2. Sensor control

    Before decoder decode on the video stream, DCE sensor control can filter out all the blurry frames that are created when the device is shaking. APIs are available on enabling or disabling sensor control, set sensor sensitivity, and check sensor status.

3. Frame filter and frame list

    DCE implements pre-treatment on all frames before they are transferred to decoders. The treated frames will be stored in the DCE frame list and send to the decoder the newest one when it finishes decoding on a previous frame. APIs are available on enabling frame filter, setting camera frame rate, and check frame filter status.

    <div align="center">
        <p><img src="overview/assets/DCE-framelist.png" width="70%" alt="How DCE works"></p>
        <p>How DCE works</p>
    </div>

4. Auto zoom

    Under the help of the barcode region prediction mode of Dynamsoft Barcode Reader, if the lastest decoded frame is predicted to contain a barcode but fails on decoding, DCE will control the camera to zoom in to approach the predicted barcode region.

## DCE working process

The following chart illustrates the DCE working process. For Android developers, DCE provides mobile device level evaluation which classifies Android devices into three different levels. Users can apply different settings on different devices.

<div align="center">
    <p><img src="overview/assets/DCE-process.png" width="50%" alt="How DCE works"></p>
    <p>DCE working process</p>
</div>

## Programming language

Dynamsoft Camera Enhancer is now available for the following programming languages:

- Java (Android)
- Objective-C & Swift (iOS)

## About this documentation

This documentation aims at helping you on learning, understanding, and using Dynamsoft Camera Enhancer. In this documentation, you can find useful information that guides you step by step from installation to further development.

## Quick links

- [Get and set up license]({{site.introduction-license}}License.html)
- [Programming guides]({{site.programming}})
- [Get help on debugging]({{site.trouble-shooting}})
- [Contact us]({{site.contact-us}})
