---
title: Motion controllers
description: 
author: GitHubUserName
ms.author: MicrosoftAlias
ms.date: 10/17/2017
ms.topic: article
keywords: 
---



# Motion controllers

Motion controllers are hardware accessories that allow users to take action in mixed reality. An advantage of motion controllers over gestures is that the controllers have a precise position in space, allowing for fine grained interaction with digital objects. For Windows Mixed Reality immersive headsets, motion controllers are the primary way that users will take action in their world.

![Windows Mixed Reality motion controllers](images/WinMR_CK_1080x1080.jpg)

## Device support

<table>
<tr>
<th>Feature</th><th style="width:150px"> HoloLens</th><th style="width:150px"> Immersive headsets</th>
</tr><tr>
<td> Motion controllers</td><td style="text-align: center;"></td><td style="text-align: center;"> ✔️</td>
</tr>
</table>



## Hardware details


<iframe width="560" height="315" src="https://www.youtube.com/embed/1nlcdDNOdm8?rel=0&amp;modestbranding=1" frameborder="0" allowfullscreen="1">

</iframe>



Windows Mixed Reality motion controllers offer precise and responsive tracking of movement in your field of view using the sensors in the immersive headset, meaning there is no need to install hardware on the walls in your space. These motion controllers will offer the same ease of setup and portability as Windows Mixed Reality immersive headsets. Our device partners plan to market and sell these controllers on retail shelves this holiday.

![Get to know your controller](images/ControllerImage.png)

**Features:**
* Optical tracking
* Trigger
* Grab button
* Thumbstick
* Touchpad

## Setup

### Before you begin

**You will need:**
* A set of two motion controllers.
* Four AA batteries.
* A PC capable of Bluetooth 4.0.

**Update Windows and Unity for motion controller support:**
1. Install the tools (Windows Insider Flight, newest Unity, etc.).
2. Check the known issues and release notes for the current software in Windows Insider flight and driver notes.

**Verify you are on the correct version of Windows:**
1. Go to **Settings**.
2. Select **System**.
3. Select the **About** tab.
4. Verify **OS Build** matches the build with motion controller support specified in Windows Insider flight and driver notes.
5. If your system shows a different build, then check for updates.

**Verify driver version:**
1. Right click on the **Windows Start Menu** and select **Device Manager**.
2. Under **Mixed Reality Devices** right-click your headset and select **Properties**.
3. Click the **Driver** tab and verify the **Driver Version** matches the driver version with motion controller support specified in Windows Insider flight and driver notes.
4. If your headset shows a different driver version, then click **Update Driver** and **Search automatically for updated driver software**

### Pairing controllers

Motion controllers can be bonded with host PC using Windows settings like any other Bluetooth device.

1.    Insert 2 AA batteries into the back of the controller. Leave the battery cover off for now.

2.    If you're using an external USB Bluetooth Adapter instead of a built-in Bluetooth radio, please review the Bluetooth Best Practices before proceeding. For desktop configuration with built-in radio, please ensure antenna is connected.

3.    Open **Windows Settings** -> **Devices** -> **Add Bluetooth or other device** -> **Bluetooth** and remove any earlier instances of “Motion controller – Right” and “Motion controller – Left”. Check also Other devices category at the bottom of the list.

4.    Select **Add Bluetooth or other device** and see it starting to discover Bluetooth devices.

5.    Press and hold the controller's Windows button to turn on the controller, release once it buzzes.

6.    Press and hold the pairing button (tab in the battery compartment) until the LEDs begin pulsing.

7.    Wait "Motion controller - Left" or "Motion controller - Right" to appear to the bottom of the list. Select to pair. Controller will vibrate once when connected. ![Select Motion controller to pair, if multiple instances select one from appearing bottom of the list](images/450px-Bluetooth_-_Add_a_device.png) 8.    You will see the controller appear in the Bluetooth settings under **“Mouse, keyboard, & pen” category”** as **Connected**. At this point, you may get a firmware update – see next section (“Updating controller firmware”).

9.    Reattach battery cover.

10.    Repeat steps 1-9 for the second controller.

After successfully pairing both controllers, your settings should look like this under “**“Mouse, keyboard, & pen” category** ![Motion controllers connected](images/450px-Motion_controller_-_connected.png)

If the controllers are turned off after pairing, their status will show up as Paired. If controllers stay permanently under “Other devices” category pairing may have been only partially completed and need to be performed again to get controller functional.

### Updating controller firmware
* If an immersive headset is connected to your PC, and new controller firmware is available, the firmware will be pushed to your motion controllers automatically the next time they're turned on. Controller firmware updates are indicated by a pattern of illuminating LED quadrants in a circular motion, and take 1-2 minutes.
* After the firmware update completes, the controllers will reboot and reconnect.
1. Both controllers should be connected now. ![Controllers connected](images/Cyk_connected.jpg)
* Verify your controllers work properly:
1. Launch **Mixed Reality Portal** and enter your Mixed Reality Home.
2. Move your controllers and verify tracking, test buttons, and verify teleportation works. If they don't, then check out [the troubleshooting section below](Motion_controllers.md#troubleshooting)

## Gazing and pointing

Windows Mixed Reality supports two key models for interaction, **gaze and commit** and **point and commit**:
* With **gaze and commit**, users target an object with their gaze and then select objects with hand air-taps, a gamepad, a clicker or their voice.
* With **point and commit**, a user can aim a pointing-capable motion controller at the target object and then select objects with the controller's trigger.

Apps that support pointing with motion controllers should also enable gaze-driven interactions where possible, to give users choice in what input devices they use.

### Managing recoil when pointing

When using motion controllers to point and commit, your users will use the controller to target and then take action by pulling its trigger. Users who pull the trigger vigorously may end up aiming the controller higher at the end of their trigger pull than they'd intended.

To manage any such recoil that may occur when users pull the trigger, your app can snap its targeting ray when the trigger's analog axis value rises above 0.0. You can then then take action using that targeting ray a few frames later once the trigger value reaches 1.0, as long as the final press occurs within a short time window. When using the higher-level composite Tap gesture, Windows will manage this targeting ray capture and timeout for you.

## Grip pose vs. pointing pose

Windows Mixed Reality supports motion controllers in a variety of form factors, with each controller's design differing in its relationship between the user's hand position and the natural "forward" direction that apps should use for pointing when rendering the controller.

To better represent these controllers, there are two kinds of poses you can investigate for each interaction source, the **grip pose** and the **pointer pose**.

### Grip pose

The **grip pose** represents the location of either the palm of a hand detected by a HoloLens, or the palm holding a motion controller.

On immersive headsets, the grip pose is best used to render **the user's hand** or **an object held in the user's hand**, such as a sword or gun. The grip pose is also used when visualizing a motion controller, as the **renderable model** provided by Windows for a motion controller uses the grip pose as its origin and center of rotation.

The grip pose is defined specifically as follows:
* The **grip position**: The palm centroid when holding the controller naturally, adjusted left or right to center the position within the grip. On the Windows Mixed Reality motion controller, this position generally aligns with the Grasp button.
* The **grip orientation's Right axis**: When you completely open your hand to form a flat 5-finger pose, the ray that is normal to your palm (forward from left palm, backward from right palm)
* The **grip orientation's Forward axis**: When you close your hand partially (as if holding the controller), the ray that points "forward" through the tube formed by your non-thumb fingers.
* The **grip orientation's Up axis**: The Up axis implied by the Right and Forward definitions.

### Pointer pose

The **pointer pose** represents the tip of the controller pointing forward.

The system-provided pointer pose is best used to raycast when you are **rendering the controller model itself**. If you are rendering some other virtual object in place of the controller, such as a virtual gun, you should point with a ray that is most natural for that virtual object, such as a ray that travels along the barrel of the app-defined gun model. Because users can see the virtual object and not the physical controller, pointing with the virtual object will likely be more natural for those using your app.

## Controller tracking state

Like the headsets, the Windows Mixed Reality motion controller requires no setup of external tracking sensors. Instead, the controllers are tracked by sensors in the headset itself.

If the user moves the controllers out of the headset's field of view, in most cases Windows will continue to infer controller positions and provide them to the app. When the controller has lost visual tracking for long enough, the controller's positions will drop to approximate-accuracy positions.

At this point, the system will body-lock the controller to the user, tracking the user's position as they move around, while still exposing the controller's true orientation using its internal orientation sensors. Many apps that use controllers to point at and activate UI elements can operate normally while in approximate accuracy without the user noticing.

The best way to get a feel for this is to try it yourself. Check out this video with examples of immersive content that works with motion controllers across various tracking states:\
 
<iframe width="560" height="315" src="https://www.youtube.com/embed/QK_fOFDHj0g?rel=0&amp;modestbranding=1" frameborder="0" allowfullscreen="1">

</iframe>



### Reasoning about tracking state explicitly

Apps that wish to treat positions differently based on tracking state may go further and inspect properties on the controller's state, such as SourceLossRisk and PositionAccuracy:

<table class="wikitable">
<tr>
<th> Tracking state </th><th> SourceLossRisk </th><th> PositionAccuracy </th><th> TryGetPosition</th>
</tr><tr>
<td> <b>High accuracy</b> </td><td style="background-color: green; color: white"> &lt; 1.0 </td><td style="background-color: green; color: white"> High </td><td style="background-color: green; color: white"> true</td>
</tr><tr>
<td> <b>High accuracy (at risk of losing)</b> </td><td style="background-color: orange"> == 1.0 </td><td style="background-color: green; color: white"> High </td><td style="background-color: green; color: white"> true</td>
</tr><tr>
<td> <b>Approximate accuracy</b> </td><td style="background-color: orange"> == 1.0 </td><td style="background-color: orange"> Approximate </td><td style="background-color: green; color: white"> true</td>
</tr><tr>
<td> <b>No position</b> </td><td style="background-color: orange"> == 1.0 </td><td style="background-color: orange"> Approximate </td><td style="background-color: orange"> false</td>
</tr>
</table>



These motion controller tracking states are defined as follows:
* **High accuracy:** While the motion controller is within the headset's field of view, it will generally provide high-accuracy positions, based on visual tracking. Note that a moving controller that momentarily leaves the field of view or is momentarily obscured from the headset sensors (e.g. by the user's other hand) will continue to return high-accuracy poses for a short time, based on inertial tracking of the controller itself.
* **High accuracy (at risk of losing):** When the user moves the motion controller past the edge of the headset's field of view, the headset will soon be unable to visually track the controller's position. The app knows when the controller has reached this FOV boundary by seeing the **SourceLossRisk** reach 1.0. At that point, the app may choose to pause controller gestures that require a steady stream of very high-quality poses.
* **Approximate accuracy:** When the controller has lost visual tracking for long enough, the controller's positions will drop to approximate-accuracy positions. At this point, the system will body-lock the controller to the user, tracking the user's position as they move around, while still exposing the controller's true orientation using its internal orientation sensors. Many apps that use controllers to point at and activate UI elements can operate as normal while in approximate accuracy without the user noticing. Apps with heavier input requirements may choose to sense this drop from **High** accuracy to **Approximate** accuracy by inspecting the **PositionAccuracy** property, for example to give the user a more generous hitbox on off-screen targets during this time.
* **No position:** While the controller can operate at approximate accuracy for a long time, sometimes the system knows that even a body-locked position is not meaningful at the moment. For example, a controller that was just turned on may have never been observed visually, or a user may put down a controller that's then picked up by someone else. At those times, the system will not provide any position to the app, and **TryGetPosition** will return false.

## Interactions: Low-level spatial input

The core interactions across hands and motion controllers are **Select**, **Menu**, **Grasp**, **Touchpad**, **Thumbstick**, and **Home**.
* **Select** is the primary interaction to activate a hologram, consisting of a press followed by a release. For motion controllers, you perform a Select press using the controller's trigger. Other ways to perform a Select are by speaking the voice command "Select". The same select interaction can be used within any app. Think of Select as the equivalent of a mouse click, a universal action that you learn once and then apply across all your apps.
* **Menu** is the secondary interaction for acting on an object, used to pull up a context menu or take some other secondary action. With motion controllers, you can take a menu action using the controller's *menu* button. (i.e. the button with the hamburger "menu" icon on it)
* **Grasp** is how users can directly take action on objects at their hand to manipulate them. With motion controllers, you can do a grasp action by squeezing your fist tightly. A motion controller may detect a Grasp with a grab button, palm trigger or other sensor.
* **Touchpad** allows the user to adjust an action in two dimensions along the surface of a motion controller's touchpad, committing the action by clicking down on the touchpad. Touchpads provide a pressed state, touched state and normalized XY coordinates. X and Y range from -1 to 1 across the range of the circular touchpad, with a center at (0, 0). For X, -1 is on the left and 1 is on the right. For Y, -1 is on the bottom and 1 is on the top.
* **Thumbstick** allows the user to adjust an action in two dimensions by moving a motion controller's thumbstick within its circular range, committing the action by clicking down on the thumbstick. Thumbsticks also provide a pressed state and normalized XY coordinates. X and Y range from -1 to 1 across the range of the circular touchpad, with a center at (0, 0). For X, -1 is on the left and 1 is on the right. For Y, -1 is on the bottom and 1 is on the top.
* **Home** is a special system action that is used to go back to the Start Menu. It is similar to pressing the Windows key on a keyboard or the Xbox button on an Xbox controller. You can go home by pressing the Windows button on a motion controller. Note, you can also always return to Start by saying "Hey Cortana, Go Home". Apps cannot react specifically to home actions, as these are handled by the system.

## Composite gestures: High-level spatial input

Both hand gestures and motion controllers can be tracked over time to detect a common set of high-level **composite gestures**. This enables your app to detect high-level **tap**, **hold**, **manipulation** and **navigation** gestures, whether users end up using hands or controllers.

## Rendering the motion controller model

**3D controller models**\
 Windows makes available to apps a renderable model of each motion controller currently active in the system. By having your app dynamically load and articulate these system-provided controller models at runtime, you can ensure your app is forward-compatible to any future controller designs.

These renderable models should all be rendered at the **grip pose** of the controller, as the origin of the model is aligned with this point in the physical world. If you are rendering controller models, you may then wish to raycast into your scene from the **pointer pose**, which represents the ray along which users will naturally expect to point, given that controller's physical design.

For more information about how to load controller models dynamically in Unity, see the Rendering the motion controller model in Unity section.

**2D controller line art**\
 While we recommend attaching in-app controller tips and commands to the in-app controller models themselves, some developers may want to use 2D line art representations of the motion controllers in flat "tutorial" or "how-to" UI. For those developers, we've made .png motion controller line art files available in both black and white below (right-click to save).

![Preview of motion controllers line art](images/MotionControllers_Black_preview.png)\
 [[Media:MotionControllers_White.png|Full-resolution motion controllers line art in '''white''']]\
 [[Media:MotionControllers_Black.png|Full-resolution motion controllers line art in '''black''']]

## FAQ

### How I can connect my controller to other PC?

*A: Currently controller support pairing with single PC at the time. Follow instructions on [motion controller setup](Motion_controllers.md#setup) to pair your controllers. Before pairing remember to remove existing paired controllers from Bluetooth & other devices so that Windows will discover the controllers.*

### How do I update motion controller firmware?

*A: Motion controller firmware is part of HMD driver and will be updated automatically on connection if required. Firmware update takes typically 1-2 minutes depending on Bluetooth radio and link quality.* *Firmeware update can occasionally can take longer up to 10 minutes, this may indicate poor Bluetooth connectivity or radio interference. Please check Bluetooth best practices below. After firmware update controller reboots and re-connects to host PC and LEDs go bright for tracking. In case firmware update is interrupted (controller powered off or battery runs out) it will be tried again on next power on.*

### How I can check battery level?

*A: Battery level is on reverse side of the virtual model, there is no physical battery level indicator. After powering on controller wait few seconds to let reading stabilize.*

### Can you use these controllers without a headset? Just for the joystick/trigger/etc input?

*A: Not for Universal Windows Applications*

## Troubleshooting

See [Troubleshooting Mixed Reality > Motion Controllers](Troubleshooting_Windows_Mixed_Reality.md#motion_controllers)

## Filing motion controller feedback/bugs

Give us feedback in Feedback Hub, using the "Mixed Reality -> Input" category.

## See also
* Gestures and motion controllers in Unity
* Gaze, gestures, and motion controllers in DirectX
* Gestures
* [Enthusiast's Guide: Your Windows Mixed Reality home](Your_Mixed_Reality_Home.md)
* [Enthusiast's Guide: Using games & apps in Windows Mixed Reality](Using_games_and_apps_in_Windows_Mixed_Reality.md)
* [Enthusiast's Guide: Tracking system](Tracking_System.md)