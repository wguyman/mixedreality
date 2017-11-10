---
title: WebVR
description: 
author: GitHubUserName
ms.author: MicrosoftAlias
ms.date: 10/17/2017
ms.topic: article
keywords: 
---


# WebVR

## What is WebVR?

[WebVR](https://webvr.info) is an open specification that makes it possible to experience VR in your browser. If a website implements WebVR support and provides 3D content, it can display immersive content in the headset, with user consent.

## What is the difference between WebVR and browsing the web in VR?

WebVR is a technology that allows a website author to add VR functionality to a page. The WebVR API is used by a page to display 3D content (such as 360 degree video, or a 3D model, or a 3D game) to the entirety of your headset. Example: Viewing a 360 Video on [cnn.com/vr](http://cnn.com/vr). If a page supports WebVR, it will add a button or other UI element that you can click to enter VR.

Browsing the web in VR means using the Edge browser while you are wearing your headset, as a 2D app within the Cliffhouse.

## Do all websites support WebVR?

No. Website authors must opt-in to use WebVR and further more may create sites that are optimized for specific browsers, headsets and controllers. For example, some WebVR content is optimized for mobile VR devices only. Also, keep in mind that web sites need to explicitly create and provide WebVR content. The number of sites that have some WebVR compatible content is growing every day.

## Can I use my Vive/Oculus etc to view WebVR content in Microsoft Edge?

No. You must use a Windows Mixed Reality headset to use WebVR in Edge. However, you may be able to access WebVR content in another browser; see the complete list of compatible devices and browsers at: [WebVR.rocks](http://webvr.rocks/).

## Where can I find the WebVR developer documentation?

The developer documentation is located here: [WebVR Developer Documentation](https://docs.microsoft.com/en-us/microsoft-edge/webvr/)

## I've found a website with WebVR that doesn't work in Windows Mixed Reality. What do I do?

You can report broken sites directly to the Microsoft Edge browser team in the [issue tracker](https://developer.microsoft.com/en-us/microsoft-edge/platform/issues/), or via twitter using [#EdgeBug hashtag](https://blogs.windows.com/msedgedev/2016/08/11/edgebug-twitter/).

You can also log bugs using the feedback tool under category:

Microsoft Edge -> Website Issues

## What is a good page to test if WebVR is working?

See [webvr.info samples](http://webvr.info/samples/XX-vr-controllers.html)

## How do I set up WebVR?

To experience WebVR content on a Windows Mixed Reality headset (using hardware or simulation) you must:
1. Ensure your headset is connected
2. Launch Microsoft Edge either on the desktop, or within Mixed Realty
3. Navigate to a WebVR enabled page
4. Click the Enter VR button within the page (the location and visual representation of this button may vary per website)
5. The first time you try to enter VR on a specific domain, the browser will ask for consent to use immersive view. Click Yes
6. Your headset should begin presenting


## See also

* [Troubleshooting > WebVR](troubleshooting-windows-mixed-reality.md#webvr)
* [How to get into your first WebVR experience](using-games-and-apps-in-windows-mixed-reality.md#how-to-get-into-your-first-webvr-experience)
* [Using games and apps in Windows Mixed Reality](using-games-and-apps-in-windows-mixed-reality.md)
* [Your Mixed Reality Home](your-mixed-reality-home.md)
* [Tracking System](tracking-system.md)
* [Motion Controllers](motion-controllers.md)
* [SteamVR](using-steamvr-with-windows-mixed-reality.md)
* [Filing feedback](filing-feedback.md)
