# Installing Microsoft Office 2010 32 bit on Ubuntu

During numerous tests, a successful installation of the Microsoft Office 2010 version for 32-bit systems was carried out. The system performance has been tested on Ubuntu 24.04 LTS system.

## Actions list step by step

### 1. Prepare i386 architecture (if you have 64 bit)
Info source:  
https://wiki.playonlinux.com/index.php/Installing_PlayOnLinux#32-bit_support_for_Ubuntu_20.04  
```
sudo dpkg --add-i386
sudo apt-get update
sudo apt-get install wine:i386
```

### 2. Install PlayOnLinux
Install PlayOnLinux using source (https://wiki.playonlinux.com/index.php/Installing_PlayOnLinux#32-bit_support_for_Ubuntu_20.04) guide.  

### 3. Prepare your MS Office 2010 32 bit installer
Install software using PlayOnLinux and following program instructions. It is recommended to install in a separate wineprefix.  
Note Microsoft core fonts will not be installed, you can close the installation window and install them manually later.

### 4. Now test it!
Try lauch any program, Word or Excel as sample. You may encounter errors when you first start, try it a couple of times.
All programs except PowerPoint will work, the setup will be described below.

## Install MS core fonts
For install MS core fonts use ultimate guide by author ibrahimtuzlak0295 (thank you):  
https://gist.github.com/ibrahimtuzlak0295/2a66981f99f25e08cb2039df53391b05.  
I will keep it for myself if the author's document is unavailable. The following is a quote from the author.  

> However, if for some reason this doesn't install the fonts, it's still possible to do that manually. First install the ttf-mscorefonts-installer package: \
> ```$ sudo apt install ttf-mscorefonts-installer``` \
> Note the prefix name: ```ls ~/.PlayOnLinux/wineprefix``` \
> And replace yourprefix in the command with the one you want: \
> ```$ cp /usr/share/fonts/truetype/msttcorefonts/* ~/.PlayOnLinux/wineprefix/yourprefix/drive_c/windows/Fonts``` \
> Now we have the core fonts in place. We can remove the package: \
> ```$ sudo apt purge ttf-mscorefonts-installer```

For selection buttons on agreement use TAB for selection and ENTER for input.

## Settings for launch PowerPoint
Thanks author BC59 from forum source https://ubuntuforums.org/showthread.php?t=1885051.  
Open your virtual disk with PowerPoint, next open Wine settings.  

> On the Libraries tab and in the New Library Override, click the small arrow and select Add ```riched20.dll``` and (IT HELPS ME!) ```gdiplus```. Then click "Edit" and, as above, change their override to ```Native (windows)```.

Now MS PowerPoint ready to works!
