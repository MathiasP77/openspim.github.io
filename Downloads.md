---
title: Downloads
layout: page
description: Installing and running the OpenSPIM software
---
# Installing the OpenSPIM/Fiji package

This is a [Fiji](https://fiji.sc/) package:

[OpenSPIM-20150426.zip (32-bit)](https://downloads.imagej.net/openspim/OpenSPIM-20150426.zip)
[OpenSPIM-20150427.zip (64-bit)](https://downloads.imagej.net/openspim/OpenSPIM-20150427.zip)

Installation:

1.  Download and unpack the right (32bit/64bit) OpenSPIM-... .zip
2.  Launch Fiji: in the *OpenSPIM.app/* folder, open *ImageJ-win32.exe* (or *-win64.exe*).
3.  Update Fiji (and OpenSPIM & µManager): *Help->Update Fiji* (or simply choose *Yes, please* if you are asked to update).
4.  Install the camera driver if needed (see below).
5.  Run Micro-Manager: *Plugins->Micro-Manager->Micro-Manager Studio*.

**Note:** if you are interested in building the software from scratch so you can modify it to your heart's extent, please have a look at [this page](How_to_build_the_software#The_easy_way).

# Drivers

Most of the drivers are shipped within [µManager](https://micro-manager.org/), bundled in our OpenSPIM software. However, some µManager drivers require separate installations (such as, in the case of the OpenSPIM version 1.0 setup, the camera driver).

## Camera Drive

Theoretically, OpenSPIM works with all cameras supported by [µManager](https://micro-manager.org/). However, OpenSPIM version 1.0 refers to the setup that has a [Hamamatsu ORCA](https://www.hamamatsu.com/eu/en/community/life_science_camera/index.html) camera. For such a setup, you need to [download and install the DCAM driver](https://www.dcamapi.com/).

If you have a QImaging camera, [download and install the QImaging drivers](https://www.qimaging.com/support/downloads/).

# Initial hardware configuration

[Hardware configuration protocol with screengrabs](https://docs.google.com/presentation/d/1DvMwhXPf1B4sVwhiWMeYxFYbZHNo7w0F9PMwoCVIO_o/edit?usp=sharing)

When Micro-Manager is first started, it will prompt the user to select a hardware configuration (defaulting to *none*).

To create a hardware configuration to use, go to *Tools->Hardware Configuration Wizard...* and select *Create new configuration.*

1.  From the Available Devices list, expand CoherentCube or Omicron and add the 'CorentCube 'or 'Omicron Laser Controller' device. Select the appropriate serial port and RS 232 settings and click OK. Ensure the BaudRate property is at 19200 for the Coherent Laser or 500000 for the Omicron laser, or the computer will not be able to communicate with the laser.
2.  From the HamamatsuHam category in the Available Devices list, add the HamamatsuHam_DCAM device. No further configuration is needed for the camera.
3.  Finally, from the PicardStage category, add in turn the twister, Z stage, and XY stage devices. The software will attempt to guess the correct serial numbers for the motors; these should be verified and corrected as necessary.
4.  Once these five devices have been added, click Next. On the following page, default devices are specified. The camera and shutter should already be set to HamamatsuHam_DCAM and CoherentCube / Omicron Laser Controller, respectively, but the user will need to set the default focus stage to Picard Z Stage. Leaving Auto-shutter enabled, click Next. The laser does not require a delay, so the setup can advance without any changes on this page. As there are no state devices to set up, the following page can also be skipped. On the final page, the user can specify a file to which the configuration will be saved before finishing the wizard.

Once the hardware configuration has been loaded, the OpenSPIM plugin can be opened using *Plugins->Acquire SPIM image*. At this point, µManager's *Snap/Live Window* will be opened along with the OpenSPIM GUI.

# And now?

Now that everything is installed and configured, let's [go & do something with it](Operation).
