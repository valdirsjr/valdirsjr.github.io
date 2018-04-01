---
layout: post
title: "HearthStone on Ubuntu"
comments: true
description: "HearthStone on Ubuntu"
keywords: "blizzard, ubuntu, hearthstone, install"
---

![Hearthstone](https://valdirsjr.github.io/assets/images/hearthstone.jpg)

Blizzard's [HearthStone](https://playhearthstone.com/) is probably the most successful computer card game ever made. Like others games from Blizzard, this one also not run (native) on Linux. But it's possible play HearthStone on Linux (in my case, a laptop + Ubuntu 16.04), in a little bit tricky way, with Wine:


### Wine

First, it's necessary install a Wine Staging version, If you already have a Wine running in your system, check the version of Wine and/or remove olders versions. 

```sh
# Check the version of Wine
wine --version
```

```sh
# Enable the Wine Staging PPA on Ubuntu
cd ~/Downloads
wget -nc https://repos.wine-staging.com/wine/Release.key
sudo apt-key add Release.key
```

```sh
# Add repository and Install Wine
sudo apt-add-repository 'https://dl.winehq.org/wine-builds/ubuntu/'
sudo apt update
sudo apt install --install-recommends winehq-staging
```


### Wine Configuration and Winetricks

Winecfg and Winetricks are the tools for a correct Wine configuration. 


#### Winecfg

To open winecfg tool just run in terminal: 
```sh
winecfg
```
In the window of Winecfg, I did some changes:

![winecfg_1](https://valdirsjr.github.io/assets/images/hs_winecfg_1.png)

I changed the Windows version to 7 (mininal to run HearthStone)

![winecfg_2](https://valdirsjr.github.io/assets/images/hs_winecfg_2.png)

I Checked CSMT, VAAPI and EAX options

![winecfg_3](https://valdirsjr.github.io/assets/images/hs_winecfg_3.png)

Tab "Libraries", in the search box you can add "locationapi", edit and set as "disabled". The others "overrides" in this list will be automatically add by the Winetricks tool, in the next step.


#### Winetricks

This tool helps a lot for the wine configuration. First, it's important to check and install the latest version of winetricks, and not the version that is listed at PPA repositories. 

```sh
# Verify the latest version of winetricks
curl --silent --show-error \
https://raw.githubusercontent.com/Winetricks/winetricks/master/src/winetricks --stderr - \
| grep ^WINETRICKS_VERSION | cut -d '=' -f 2
```

```sh
# Check the currently installed version
winetricks --version
```

```sh
# Remove winetricks (if you have a older version)
sudo apt-get remove winetricks
```

```sh
# Install the latest version
wget  https://raw.githubusercontent.com/Winetricks/winetricks/master/src/winetricks
chmod +x winetricks 
sudo mv -v winetricks /usr/local/bin
```

To run winetricks

```sh
# Run winetricks
winetricks
```

First, check "Select the default wineprefix" to use the currently config:

![wt_1](https://valdirsjr.github.io/assets/images/wt1.png)

After, it's necessary check "Install a Windows DLL" to install two important components: `ie8` and `d3dx9`. Also, may be necessary install `corefonts` on "Install a font" option:

![wt_2](https://valdirsjr.github.io/assets/images/wt2.png)


### Install Battle.net

The easiest part is install Blizzard Battle.net and Hearthstone. Just [download the Battle.net](https://us.battle.net/account/download/) and run by clicking on `exe` file. Follow instructions like in a Windows install, and no more problems after that. 

![screen_1](https://valdirsjr.github.io/assets/images/screen1.png)

![screen_2](https://valdirsjr.github.io/assets/images/screen2.png)


### Notes

In some websites I read about options to add in the command line to run Hearthstone, but wasn't necessary for me. 

```
-force-d3d9
-dx9
```

---
References:

[https://www.maketecheasier.com/play-hearthstone-on-ubuntu-linux/](https://www.maketecheasier.com/play-hearthstone-on-ubuntu-linux/)

[https://askubuntu.com/questions/755059/how-do-i-get-the-latest-version-of-winetricks-on-ubuntu](https://askubuntu.com/questions/755059/how-do-i-get-the-latest-version-of-winetricks-on-ubuntu)
