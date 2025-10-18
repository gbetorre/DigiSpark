# DigiSpark
Italian localization of the library for programming the Digispark ATTiny85 8-bit microcontroller.

# Emulation of USB peripherals via microcontrollers and cybersecurity risk

**_Essay by G. Torre_**
&copy; G. Torre, 2021

## Introduction

The USB ports, in modern computers world, are everywhere! As a matter of fact, they are extremely convenient but, as we'll see in this article, they also poses significant security risks.

From one hand, USB ports on PCs and Macs allow data to be exchanged between a large number of devices and the personal computer, making it easy to add peripherals without worrying about restarting the system or device recognition. Last but not least, they also provide a moderate voltage that can be used to charge low-power devices. 

On the other hand, these conveniences come at a price in terms of vulnerability, and every USB port is effectively an open door to the potential risk of unauthorized access to the system and the destruction of data or, worse, to the insertion of malicious code that can cause severe issues for privacy and data security.

---

The first widely known commercial device capable of carrying out attacks via a USB port was the Rubber Ducky. However, this peripheral required knowledge of a specific language for script programming and had its own architecture.

Today, however, thanks to the spread of microcontrollers (especially those compatible with Arduino), it has become possible to build customized devices of this type, which can be “disguised” as USB sticks and, being developed ad hoc, are particularly difficult to detect by security software (such as antivirus programs). 
The “flashing” task is further simplified by using Digispark, an Arduino-compatible microcontroller. The set of commands for programming exploits is simply the standard Arduino set and, above all, the technical characteristics of this microcontroller (16 MHz at 5V) allow these boards to be disguised as USB peripherals (mice, joysticks, or keyboards), providing the system with commands that have been preloaded via sketches.

This type of attack can be carried out on all platforms: Windows, Mac, and Linux, after customizing the scripts and syntax of the commands to be executed. 

Below, we will explore the implementation and programming details of these interesting  microcontrollers, as well as their counterpart in terms of cybersecurity risks.
