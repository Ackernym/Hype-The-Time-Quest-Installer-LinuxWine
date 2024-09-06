Hype The Time Quest Alternative Installer (Linux Wine)
===========================================

A Slight modification of the original Alternative Installer in order to better work when installing Hype using wine or one of its frontends on Linux.

  I've found that in order to install Hype using wine, the windows version needds to be set to 'Windows NT 4.0' as well as the prefix being 32bit (in bottles this is done by editinig the registry, specifically adding a string value of 'Version' to HKEY_CURRENT_USER/Software/Wine and the setting the value to be 'nt40' as referenced in this issue: https://github.com/bottlesdevs/Bottles/issues/1952).

The problem I've encountered is that in order to install Hype, you normally need to use a program like cdemu with a .bin and .cue file to virtually mount Hype so that the original installer recognizes the cd. Personally, I would rather install Hype without resorting to external tools like cdemu to spoof a disc drive. Unfortunately setting the windows version in wine to NT means that the Alternative installer cannot work as the version of inno setup it was created in no longer works with that version of windows. I recompiled the installer in 5.4.3 so that it would work in windows NT. I also changed the installer to add the contents of \exe\DLL MFC from the CD to the root directory of the installed game as the game will not run unless those files are present in the wine prefix. 

In addition, I also added the video direcotry and the options directory from the \gamedata directory on the CD to the \gamedata directory of the installed game. I also slightly reconfigured the ubi.ini file to default to playing the video, although this will cause graphical glitches, so I reccommend turning it to 0 once you've watched the intro videos once. 

Lastly, I'm also aware this is a MESSY readme, so at somepoint I'll clean it up, and I'll probably clean up a couple naming conventions in the installer itself too.



Below is the original ReadMe:

An alternate installer for _Hype The Time Quest_, written using [Inno Setup](http://www.jrsoftware.org/isinfo.php)
to replace the original 16-bit InstallShield installer.

This project uses code from both [bgbennyboy](https://github.com/bgbennyboy)'s [_Grim Fandango Setup_](https://github.com/bgbennyboy/Grim-Fandango-Setup-and-Launcher)
and [Triangle717's](http://Triangle717.WordPress.com) LEGO Racers installer.

The installer comes also bundled with nGlide.
