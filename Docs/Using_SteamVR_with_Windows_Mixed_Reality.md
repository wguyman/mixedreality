---
title: Using SteamVR with Windows Mixed Reality
description: 
author: GitHubUserName
ms.author: MicrosoftAlias
ms.date: 10/17/2017
ms.topic: article
keywords: 
---



# Using SteamVR with Windows Mixed Reality

The Windows Mixed Reality SteamVR preview allows developers to test and optimize their SteamVR experiences to run on Windows Mixed Reality headsets. This program is currently in an invite-only **closed preview.** while we work with a limited set of developers to uncover stability and performance issues. We will be making the preview available to all consumers on Steam Early Access this holiday season so stay tuned for a broader preview release. If you have not yet joined our developer program and are interested in participating, please sign up at [aka.ms/iwantmr](http://aka.ms/iwantmr).

## Hardware recommendations

In addition to the [Ultra PC requirements for running Windows Mixed Reality](Windows_Mixed_Reality_minimum_PC_hardware_compatibility_guidelines.md), we recommend running the SteamVR Preview on a PC with a GTX 1070 video card (or better) and an Intel Core i7 processor. We are continuing to review feedback and optimize the performance to support additional system configurations in future updates. If your PC does not meet these specs you won't be blocked from running the Windows Mixed Reality SteamVR preview however this will impact the performance and quality of the overall experience.

## Initial setup instructions

### Install the Windows 10 Fall Creators Update

You must be running the latest Windows 10 Fall Creators update to use the Windows Mixed Reality SteamVR preview.

### Setting up SteamVR
1. Install Steam - http://store.steampowered.com/about. **Note:** If you already have Steam and you're running the client beta, you'll need to opt out before proceeding - Steam (top left of the UI) -> Settings -> Account -> Beta Participation - Not Participating.
2. Install SteamVR - Use the drop down under your Library to filter to Tools and then locate SteamVR in the list and right click to install.
3. Open SteamVR properties - right click SteamVR in the same Tools page and open the Properties dialog.![Install SteamVR from the tools section of your Steam Library](images/SteamVR_install.png)
4. Join the SteamVR Beta - click the Betas tab and opt into SteamVR Beta Update by selecting it from the drop down. **Note:** The beta access code field should be left blank and you can just hit close to confirm.![Switch to the SteamVR beta in the properties dialog for SteamVR](images/SteamVR_Beta.png)

### Enable Developer mode in Windows settings

Windows Settings -> Update and Security -> For developers - Select Developer Mode![Enable Developer mode in Windows Settings](images/SteamVR_DevMode.png)

### Activate the Windows Mixed Reality SteamVR Preview

The Windows Mixed Reality SteamVR preview is currently in a **closed developer preview** so you must have a key to download it on Steam. Once you receive your key, activate the product through Steam:

Under the "Games" drop down menu at the top left of your Steam Client select "Activate a Product on Steam" -> Next -> Accept -> copy/paste your key -> Next -> Finish![Use the product key to obtain your download of the SteamVR preview](images/SteamVR_ActivateProduct.jpg)

### Install the Windows Mixed Reality SteamVR preview
1. Filter your Steam Library to ‘Software’ to find the Windows Mixed Reality SteamVR preview that you just activated with the product key
2. Select it in the list and click Install

## Launching and playing Steam games

Once you've installed the SteamVR preview according to the directions above you should be ready to play VR games from your personal Steam library. To play titles from your collection:
1. Close SteamVR if its already running
2. Launch the Mixed Reality Portal and make sure you make it to the Windows Mixed Reality Home and that your controllers are working correctly
3. Use Steam to download and launch the title you wish to play or launch them directly from a shortcut on your desktop (if asked, choose to launch in SteamVR mode).

Note: If you lock your screen, remove your headset, switch users or if your PC goes to sleep Steam will exit

## Controls

The basic controls in games are controlled by the app developer but the high level system controls are as follows:
1. Click down the **left analog thumbstick** to bring up the **Steam Dashboard**.
2. Click down the **right analog thumbstick** to switch your **controller handedness** (older SteamVR titles may have been designed for identical Vive controllers that weren't specific to left and right handedness).
3. Use the **Windows button** to return to the **Windows Mixed Reality home**.

## Staying up-to-date

After you've completed the setup staying up to date is easy. You can pull the latest version from Steam by checking for updates under the downloads section of your Library. If you have auto-updates enabled, then the Windows Mixed Reality SteamVR preview will stay up to date automatically.

## Tuning your App for Windows Mixed Reality

Below is an overview of common adjustments developers can make to ensure their experience is tuned for Windows Mixed Reality.
1. If your app renders controller models:
* Use the [Windows Mixed Reality motion controller models](Motion_controllers.md#rendering_the_motion_controller_model)
* Use IVRRenderModel::GetComponentState to get local transforms to component parts (eg. Pointer pose)
2. If your application shows button layouts, controller tutorials, or any other UI directly related to platform specific controllers, update them to include Windows Mixed Reality Motion Controller layouts.
3. Experiences that have a notion of handedness should get hints from the input APIs to differentiate controllers (Unity example)
4. If possible, default to thumb stick based teleportation to match the Windows Mixed Reality home teleportation behavior

## Bugs and feedback

Your feedback is invaluable when it comes to improving the Windows Mixed Reality SteamVR preview experience. Please submit all feedback and bugs through the Windows Feedback Hub. Please select the **Mixed Reality** category, and put the word **SteamVR** in the problem summary.

If you have questions or comments to share, you can also reach us on our [Steam forum](http://steamcommunity.com/app/719950/discussions/).

## FAQs and troubleshooting

### SteamVR won't launch or continuously crashes
1. Launch the Mixed Reality Portal and make your way to the Windows Mixed Reality Home, then try launching SteamVR again
2. Make sure your PC is in developer mode
3. Double check that you opted into the SteamVR beta
4. Confirm that you aren't running a Beta version of the Steam client

### My controllers aren't working as expected
1. Close SteamVR
2. Return to the Windows Mixed Reality Home and confirm that your controllers are working as expected
3. Launch the experience again and your controllers should be back to normal
4. If issues persist please file feedback using the Windows Feedback Hub

### My games are running slowly
1. Pause the preview (display mirror) in the Mixed Reality Portal
2. Confirm you're running against the recommended specs for the Windows Mixed Reality Preview
3. Confirm you're running against the recommended specs for the game located on the Steam page

### SteamVR is Showing a Compositor Error
1. If you have multiple graphics adapters, the main monitor and Mixed Reality HMD should be connected to the same adapter

## See also
* Install the tools
* Developer readiness status
* Windows Insider flight and driver notes
* [Windows Mixed Reality minimum PC hardware compatibility guidelines](Windows_Mixed_Reality_minimum_PC_hardware_compatibility_guidelines.md)