How to get this working for you, the simple version:

PRE-REQUISITES:
* required software:
  - fatsort, udisk, kde-baseapps-bin
      install via your package manager, eg, from a console, do:
        sudo apt-get install fatsort udisk kde-baseapps-bin
      the kde base apps binaries package is required for kdialog. This script
      could also be modified to use zenity for other shells, if you really want
      it. Since I've had enough of GNOME, I haven't bothered to extend this
      script to go there -- but if someone wants it, just shout.
  - devmon
      this is a script which I didn't write. You can get the original author's
      version from:
      http://igurublog.wordpress.com/downloads/script-devmon/
      You will have to rename it to "devmon" and place alongside devmon_local.
      Alternatively, use the bundled version for which I take no responsibility:
      it's included just to make your life easier and could be removed if the
      original author requests so.

* permissions:
 - you must have full read-write permissions for removable storage block 
    devices. To do this, you will probably have to be part of the "disk"
    group. An easy way to do this is, from a console:
      sudo usermod $(whoami) -G $(groups | tr " " ","),disk
    After you've authenticated to sudo, log out and back in again.

Actual installation:

1) copy devmon, devmon_local and sort_on_unmount to somewhere in your home 
  (I have a scripts  folder in my home folder, for example)
2) in KDE, launch the Autostarts manager (click the "K" and type "autostarts"
  to find it) and add devmon_local as a startup script. If you're not using KDE
  then you can use the startup manager for your desktop to do this (GNOME and
  XFCE have interfaces for this, IIRC). The script can be included as a symlink
  in the startup process as it uses readlink to get back to it's "living
  quarters" to find the devmon script

That's it. Really. You will have to log out and back in again to see it working.

