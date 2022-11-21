---
title: Setting up project
date: 2022-11-05
tags: ["unity", "meta-qeust"]
---
# Connecting the Meta Quest 

Problem: If connecting the Meta Quest with a Linux machine, the device is not listed on the connected devices.

Solution: Adjusting the android rules to grant permission for the meta quest.

Device USB information:

```console
Bus 001 Device 017: ID 2833:0182 
```

Adding the following line to the android rules file:

```console
SUBSYSTEM=="usb", ATTR{idVendor}=="2833", ATTR{idProduct}=="0182", MODE="0666", GROUP="plugdev"
```

Now the Meta Quest Device shows up when connecting via and USB-C/ USB cable. 

# Unity Setup for Meta Quest

Installing the required packages to get the Meta Quest running on a Linux machine with Unity.

Steps that have been performed:

- custom install of jdk and android sdk tools for linux
- installing the latest stable version of Unity with Android Build Support
- getting the Oculus Integration SDK Package from the Unity Asset Store 
- updating OVRPlugin manually after installing XR integration 
- creating a developer account on the MetaQuest page and setup 2-factor authentification for verification
- enable Developer Mode for the device via the Meta Quest App on the mobile phone

# Testing Meta Quest in Unity

Now, I want to check if I can actually construct a sample scene in Unity and show it on the Meta Quest device.

First of all, I had to locate Unity on the headset by searching for "Unknown Sources" in the App Managment section.

Then, I openend Unity and selected a random sample scene from the Assets/Oculus/SampleFramework/Usage folder.

I dragged the scene into my Unity project and built the scene with the Oculus headset as selected device, which took a while.

After that, I put on the headset and saw that I was located in an empty Unity scene. 

So, I've got some good and some bad news:

1.) I got the Meta Quest connected to Unity (yay!)
2.) But, unfortunately, the scene that was shown was not the same as the sample scene I have selected

Guess, now I have to figure out how to represent the sample scene to be shown on the Meta Quest.

(tbc)