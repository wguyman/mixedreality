---
title: Windows Mixed Reality minimum PC hardware compatibility guidelines
description: 
author: GitHubUserName
ms.author: MicrosoftAlias
ms.date: 10/17/2017
ms.topic: article
keywords: 
---


# Windows Mixed Reality minimum PC hardware compatibility guidelines

**NOTE:** guidelines for development PCs are higher than those for consumers' PCs running mixed reality apps.

Performance may vary depending on your exact setup. You'll also need to make sure your PC has the [right ports](recommended-adapters-for-windows-mixed-reality-capable-pcs.md) for the Windows Mixed Reality immersive headset that you are using.

## Windows Mixed Reality PC Check

![Screenshot of Windows Mixed Reality PC Check](images/screenshot-mr-pc-check.jpg) 
<a class="doc-storelink" href="https://www.microsoft.com/store/productid/9NZVL19N7CNC"><div>
<div>
Windows Mixed Reality PC Check
</div><div>
Microsoft Corporation
</div><div>
Available for free in the Microsoft Store
</div>
</div><div>
<img alt="Windows Mixed Reality PC Check icon" width="150" height="150" src="images/store-icon-windows-mixed-reality-pc-check.png" />
</div></a>


The *Windows Mixed Reality PC Check* app is the best way to make sure your PC is ready to run mixed reality. Upon running the app, you'll get one of the following messages:
* **You're good to go.** Your PC has what it takes to run Windows Mixed Reality.
* **You’re nearly there.** This PC may be able to run Windows Mixed Reality, but some features might be limited.
* **Can't run mixed reality.** This PC doesn't meet the minimum requirements needed to run Windows Mixed Reality.

You will then get an analysis of your PC against the required hardware, drivers, and operating system.

<table>
<tr>
<th></th><th> What it means</th>
</tr><tr>
<td> <img alt="Succeeded" width="60" height="60" src="images/glyph-succeeded.png" /></td><td> Your PC passes the required item.</td>
</tr><tr>
<td> <img alt="Warning" width="60" height="60" src="images/glyph-warning.png" /></td><td> There may be issues with your PC for the given requirement. If you encounter issues, you may need to troubleshoot or upgrade your PC.</td>
</tr><tr>
<td> <img alt="Error" width="59" height="60" src="images/glyph-error.png" /></td><td> Your PC does not meet the requirements for the specified item.</td>
</tr>
</table>



## Compatibility guidelines
> [!NOTE]
> We will be updating, making additions to and may be revising these Windows Mixed Reality PC Compatibility Guidelines. Please check back regularly for the latest guidelines and requirements.

<table>
<tr>
<th style="width:20%"></th><th style="width:40%">Windows Mixed Reality Ultra PCs<br /><img alt="Windows Mixed Reality Ultra badge" width="104" height="147" src="images/Badge-windows-mixed-reality-ultra-pc.png" /></th><th style="width:40%">Windows Mixed Reality PCs<br /><img alt="Windows Mixed Reality badge" width="103" height="120" src="images/Badge-windows-mixed-reality-pc.png" /></th>
</tr><tr>
<td>Operating System</td><td colspan="2" style="vertical-align: middle; text-align: center;">Windows 10 Fall Creators Update (RS3) - Home, Pro, Business, Education</td>
</tr><tr>
<td>Processor</td><td>Intel Core i5 4590 (4th generation), quad core (or better) AMD Ryzen 5 1400 3.4Ghz (desktop), quad core (or better)</td><td>Intel Core i5 7200U (7th generation mobile), dual core with Intel&#174; Hyper-Threading Technology enabled (or better)</td>
</tr><tr>
<td>RAM</td><td>8GB DDR3 (or better)</td><td>8GB DDR3 dual channel (or better)</td>
</tr><tr>
<td>Free disk space</td><td colspan="2" style="vertical-align: middle; text-align: center;">At least 10 GB</td>
</tr><tr>
<td>Graphics Card</td><td>NVIDIA GTX 960/1050 (or greater) DX12-capable discrete GPU AMD RX 460/560 (or greater) DX12-capable discrete GPU GPU must be hosted in a PCIe 3.0 x4+ Link slot</td><td>Integrated Intel&#174; HD Graphics 620 (or greater) DX12-capable integrated GPU <a href="https://en.wikipedia.org/wiki/List-of-Intel-graphics-processing-units#Ninth-generation">(Check if your model is greater)</a> NVIDIA MX150/965M (or greater) DX12-capable discrete GPU</td>
</tr><tr>
<td>Graphics Driver</td><td>Windows Display Driver Model (WDDM) 2.2 (7/17/2017 or later)</td><td>Windows Display Driver Model (WDDM) 2.2 (7/24/2017 or later)</td>
</tr><tr>
<td><a href="Recommended-adapters-for-Windows-Mixed-Reality-Capable-PCs.md">Graphics display port</a></td><td>HDMI 2.0 or DisplayPort 1.2</td><td>HDMI 1.4 or DisplayPort 1.2</td>
</tr><tr>
<td>Display</td><td colspan="2" style="vertical-align: middle; text-align: center;">Connected external or integrated VGA (800x600) display (or better)</td>
</tr><tr>
<td><a href="Recommended-adapters-for-Windows-Mixed-Reality-Capable-PCs.md">USB connectivity</a></td><td colspan="2" style="vertical-align: middle; text-align: center;">USB 3.0 Type-A or Type-C</td>
</tr><tr>
<td>Bluetooth connectivity (for <a href="Motion-controllers.md">motion controllers</a>)</td><td colspan="2" style="vertical-align: middle; text-align: center;">Bluetooth 4.0</td>
</tr><tr>
<td>Expected headset framerate</td><td>90 Hz</td><td>60 Hz</td>
</tr>
</table>



**Notes:**
* Larger laptops (with screens of at least 15”) perform best.
* Hybrid graphics configurations are compatible only with a Windows Mixed Reality Ultra setup. The hybrid system’s discrete card must meet the same specifications listed for Windows Mixed Reality Ultra above.
* Different headsets may require different hardware ports, so make sure your PC has the correct ports or [port adapters](Recommended-adapters-for-Windows-Mixed-Reality-Capable-PCs.md) to connect to your headset.

*Discrete and integrated graphics hardware that don't meet the minimum confirmed specifications have not been tested, confirmed, or optimized for Windows Mixed Reality and may not function properly or at all.*

## See also
* [Recommended adapters for Windows Mixed Reality capable PCs](recommended-adapters-for-windows-mixed-reality-capable-pcs.md)
