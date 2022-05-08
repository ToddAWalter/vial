# Vial

## About
Vial is an open-source spectral warping wavetable synthesizer. 

This is an unofficial fork of the mtytel/vital repository. 

Modifications here are minimal and are mostly aimed at making the project a bit more vanilla and suitable for local development. The following changes have been made.

- Removed all things cloud based that require an account
  - Initial log in UI and authentication classes
  - Preset download dialog
  - Text to Wavetable function
  - Check for updates option
- Remove commercial branding (WIP)

The build process for the standalone app and the AU plugin is very straightforward. Building the VST plugin is a bit tricky as you currently need the VST2 API and it can't be distributed.

## Building (Mac)

These instructions are for a Mac but can be easily adapted to Windows or Linux. In time, I'll add instruction for those platforms as well.

### Prerequisites

#### Projucer

Vial makes use of the [Juce](https://juce.com/) framework. After you have understood what Juce is you should start by installing [Projucer](https://juce.com/discover/projucer). Projucer will come with a current stable version of Juce but all we need is the Projucer application. In fact, the Juce framework version used to build Vial is located in the [third_party](/third_party/) folder and is distributed with this codebase.

#### XCode

Not going to go on about what XCode is. You get it in the App Store. It's free.

### Standalone App Instructions

#### Generate project in Projuce

Open Projucer. In the file menu select Open.. and navigate to the [standalone folder](standalone) and select the vial.jucer file. It should open in Projucer. In the top of the Projucer window you should see "XCode (macOS) - builds/osx" as the selected exporter. Click the icon to the right. 

#### Build project in XCode

The project should now be open in XCode. If you are looking to build an app that you want to actually play for fun then make sure you go to Product > Scheme > Edit Scheme... You should set the Build Configuration to Release. A Debug build will sound like crap once you press more than a couple of keys.

### Plugin (VST/AU) Instructions

The current version of Vial requires the Steinberg VST2 API even to build VST3. However, that API is deprecated and one cannot distribute any plugin built with it without having signed an agreement with them back when the agreement was still available. The SDK itself is very hard to find and I cannot distribute it here you'll have to [find it for yourself](https://web.archive.org/web/20181016150224if_/https://download.steinberg.net/sdk_downloads/vstsdk3610_11_06_2018_build_37.zip).

If you just want to build an AU plugin you can skip the VST stuff.

#### Install Legacy VST2 SDK

Once you have obtained the SDK, extract it to e.g. /third_party/VST_SDK/VST2_SDK. The folder should have a "plugininterfaces" and "public.sdk" folder inside.

#### Set Global Path for VST2 in Projucer

Open the vial.jucer file in the [plugin](/plugin/) directory with Projucer. In the Projucer main menu select Projucer > Global Paths... In the Global Paths dialog click the ellipsis button next to the VST (Legacy) SDK field and navigate to your VST2_SDK folder.

Follow the instructions for the standalone build. It's essentially the same.

## License
The source code is licensed under the GPLv3. If you download the source or create builds you must comply with that license.
