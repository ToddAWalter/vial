# Vial

## About
Vial is an open-source spectral warping wavetable synthesizer. 

This is an unofficial fork of the mtytel/vital repository. 

Modifications here are minimal and are mostly aimed at making the project a bit more vanilla and suitable for local development. The following changes have been made.

- Removed all things cloud based that require an account
  - Log in dialogs
  - Preset downloads
  - Text to Wavetable
  - Branding (WIP)
  - Check for Updates


The build process for the standalone app and the AU plugin is very straightforward. Building the VST plugin is a bit tricky as you currently need the VST2 API and it can't be distributed.

## Building The Standalone Application on Mac

These instructions are for a Mac but can be easily adapted to Windows or Linux. In time, I'll add instruction for those platforms as well.

### Prerequisites

#### Projucer

Vial makes use of the [Juce Framework](https://juce.com/). After you have understood what Juce is you should start by installing [Projucer](https://juce.com/discover/projucer). Projucer will come with a current stable version of Juce but all we need is the Projucer application. In fact, the Juce framework version used to build Vial is located in the [third_party](/third_party/) folder and is distributed with this codebase.

#### XCode

Not going to go on about what XCode is. You get it in the App Store. It's free.

### Instructions

Open Projucer. In the file menu select Open.. and navigate to the [standalone folder](standalone) and select the .jucer file. It should open in Projucer. In the top of the Projucer window you should see "XCode (macOS) - builds/osx" as the selected exporter. Click the icon to the right. 

The project should now be open in XCode. If you are looking to build an app that you want to actually play for fun then make sure you go to Product > Scheme > Edit Scheme... You should set the Build Configuration to Release. A Debug build will sound like crap once you press more than a couple of keys.


I'll try to update this readme with more general build instructions as I have time.

## License
The source code is licensed under the GPLv3. If you download the source or create builds you must comply with that license.
