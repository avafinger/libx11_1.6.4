# libx11_1.6.4 fix

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

## Steps to reproduce

* Boot Up your PC with Ubuntu and enter the Lubuntu session.
* attach a SDHC USB reader with a media with a huge tree of directories and subdirectories.
* Navigate inside every directory and sub directory very fast, i mean it, click, click, click as fast as you can.
* At some point you get **pcmanfm** stuck for a while and then a crash. It can occur in a few clicks or take some time to occur.

Google chrome is also affected by this bug, always at the startup of the application, if Google chrome takes a long time to show up on screen it usually will present you with the annoying "**!xcb_xlib_threads_sequence_lost**" error.

## Installation

If you install these deb packages you will prevent any further update coming from the ubuntu team with a possible fix. Since it has been a long time with this bug around that this proposed fix worth a shot, i could never work with Geany crashing from time to time.

Install:

    sudo dpkg -i libx11-6_1.6.4-3ubuntu0.3_amd64.deb
    sudo dpkg -i libx11-xcb1_1.6.4-3ubuntu0.3_amd64.deb
    sudo dpkg -i libx11-xcb-dev_1.6.4-3ubuntu0.3_amd64.deb
    sudo dpkg -i libx11-dev_1.6.4-3ubuntu0.3_amd64.deb
    

## disclaimer

There is no garantee it will work for you as it worked for me.
Update at your own risk.
