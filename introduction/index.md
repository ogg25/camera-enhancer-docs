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

Dynamsoft Camera Enhancer (DCE) is an SDK specifically designed for improving video frame decoding. Before video frames are transferred for decoding, DCE will do a series of preprocessing including camera control and frame filter. This step can largely reduce the rate of misreading barcodes. DCE can be integrated at the start of your developer or you can import the DCE algorithm into your already developed application to improve its performance. 

## Main features

1. Auto focus

    If the device's default auto focus is not sensitive enough, DCE can provide a specially designed auto focus mode that can largely improve camera focus efficiency. Diversiform APIs also enable the user to make personalized focus settings to reach various requirements.

2. Sensor control

    Before using the decoder to decode a video stream, DCE sensor control can filter out all the blurry frames that are created when the device is shaking. APIs are available for enabling or disabling sensor control, setting sensor sensitivity and for checking sensor status.

3. Frame filter and frame list

    DCE implements pre-treatment on all frames before they are transferred to the decoder. The treated frames will be stored in DCE's frame list and sent to decoder with the newest being sent once it has finished decoding the previous frame. APIs are available on enabling frame filter, setting camera frame rate and check frame filter status.

    <div align="center">
        <p><img src="overview/assets/DCE-framelist.png" width="70%" alt="How DCE works"></p>
        <p>How DCE works</p>
    </div>

4. Auto zoom

    Under the help of barcode region predition mode of Dynamsoft Barcode Reader, if the lastest decoded frame is predicted to contain a barcode but failing to decode, DCE will control the camera to zoom in to approach the predicted barcode region.

## DCE working process

The following chart illustrates DCE working process.

<div align="center">
    <p><img src="overview/assets/DCE-process.png" width="50%" alt="How DCE works"></p>
    <p>DCE working process</p>
</div>

## Programming language 

Dynamsoft Camera Enhancer is now available for following programming languages:

- Java (Android)
- Objective-C & Swift (iOS)

## About this documentation

This documentation aims at helping you with learning, understanding and using Dynamsoft Camera Enhancer. In this documentation you can find useful information that will guide you step by step from installation to further development. 

## Quick links

- [Get and set up license]({{site.introduction-license}}License.html)
- [Programming guides]({{site.programming}})
- [Get help on debugging]({{site.trouble-shooting}})
- [Contact us]({{site.contact-us}})
