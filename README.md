# libx11_1.6.4 bug fix

This is the Ubuntu 18.04 libx11_1.6.4 with the proposed Fix for the poll_for_response race condition bug.
The bug affects the following applications and desktops i have used so far.

**Desktops**

* lubuntu desktop
* LXDE desktop

**Applications**
* Geany
* Leafpad
* pcmanfm
* Google Chrome

**Leafpad Crash screenshot**

![Leafpad crash](https://raw.githubusercontent.com/avafinger/libx11_1.6.4/libx11-1.6.4-4/leafpad_crash.png)


**Bug**

![Leafpad bug](https://raw.githubusercontent.com/avafinger/libx11_1.6.4/libx11-1.6.4-4//xcb_xlib_threads_sequence_lost_bug.png)


## Steps to reproduce

* Boot Up your PC with Ubuntu and enter the Lubuntu session.
* attach a SDHC USB reader with a media with a huge tree of directories and subdirectories.
* Navigate inside every directory and sub directory very fast, i mean it, click, click, click as fast as you can.
* At some point you get **pcmanfm** stuck for a while and then a crash. It can occur in a few clicks or take some time to occur.

Google chrome is also affected by this bug, always at the startup of the application, if Google chrome takes a long time to show up on screen it usually will present you with the annoying "**!xcb_xlib_threads_sequence_lost**" error.

## Installation

The **xcb_xlib_threads_sequence_lost** bug has been around for a long time and if you work with **Text apps** like **Leafpad**, **Geany**, or any other Editor or application that you must not lose your work when this application crash, then you should try this fix. Unfortunately the latest Google-Chrome and Chromium-browser version **85** will crash but not the version **84**, **Firefox** works just fine.

**Update**

Currently it is woking fine with (I think they fixed the issue with **xcb_xlib_threads_sequence_lost** on the browser side):

* Chromium, Version 90.0.4430.72 (Official Build) Built on Ubuntu , running on Ubuntu 18.04 (64-bit)
* Chrome, Version 90.0.4430.85 (Official Build) (64-bit)
* FireFox, 87.0 (64-bit)


**Install:**

    sudo dpkg -i libx11-6_1.6.4-3ubuntu0.4_amd64.deb
    sudo dpkg -i libx11-xcb1_1.6.4-3ubuntu0.4_amd64.deb
    sudo dpkg -i libx11-data_1.6.4-3ubuntu0.4_all.deb
    sudo dpkg -i libx11-doc_1.6.4-3ubuntu0.4_all.deb
    sudo dpkg -i libx11-xcb-dev_1.6.4-3ubuntu0.4_amd64.deb
    sudo dpkg -i libx11-dev_1.6.4-4ubuntu0.4_amd64.deb
    

## Releases

version: 1.6.4-3ubuntu0.4 with latest SECURITY UPDATE

https://github.com/avafinger/libx11_1.6.4/releases/tag/v0.9

    libx11 (2:1.6.4-3ubuntu0.3) bionic-security; urgency=medium

      * SECURITY UPDATE: integer overflow and heap overflow in XIM client
        - debian/patches/CVE-2020-14344-1.patch: fix signed length values in
          modules/im/ximcp/imRmAttr.c.
        - debian/patches/CVE-2020-14344-2.patch: fix integer overflows in
          modules/im/ximcp/imRmAttr.c.
        - debian/patches/CVE-2020-14344-3.patch: fix more unchecked lengths in
          modules/im/ximcp/imRmAttr.c.
        - debian/patches/CVE-2020-14344-4.patch: zero out buffers in functions
          in modules/im/ximcp/imDefIc.c, modules/im/ximcp/imDefIm.c.
        - debian/patches/CVE-2020-14344-5.patch: change the data_len parameter
          to CARD16 in modules/im/ximcp/imRmAttr.c.
        - debian/patches/CVE-2020-14344-6.patch: fix size calculation in
          modules/im/ximcp/imRmAttr.c.
        - debian/patches/CVE-2020-14344-7.patch: fix input clients connecting
          to server in modules/im/ximcp/imRmAttr.c.
        - CVE-2020-14344
      * SECURITY UPDATE: integer overflow and double free in locale handling
        - debian/patches/CVE-2020-14363.patch: fix an integer overflow in
          modules/om/generic/omGeneric.c.
        - CVE-2020-14363


## disclaimer

While it fix the **!xcb_xlib_threads_sequence_lost** bug, it breaks Chrome and Chromium browser **version 85**. Firefox is not affected.
Works with latest Browser!

