# pfSense 101

## Introduction

This repo is for information about pfSense, Netgate, Unifi, and other basics that a user may need to setup a secure home network. It geared towards users with an average skill level, and I will also assume that most want Wifi capability.

You will notice that I suggest hardware that may need to be purchased, but some of may be done with hardware you have on hand already. Power users may prefer to build their own solutions and take a different approach.

Some helpful scripts will be included in the repo if you wish to use them. There are a lot of videos in this guide, and if you do not like learning via video then you might want to look elsewhere. I think the average user will really enjoy how powerful this setup can be!

## Table of Contents
* [**1. Main Documentation Sources**](https://github.com/gH7aerakaGpLTYrwVTa/pfSense101/blob/master/README.md#main-documentation-sources)
* [**2. Let's Get Started**](https://github.com/gH7aerakaGpLTYrwVTa/pfSense101/blob/master/README.md#lets-get-started)
* [**3. Holder**]() 
* [**4. Holder**]()
* [**5. Holder**]()
* [**6. Backups**]()

## Main Documentation Sources

- [Netgate Docs](https://docs.netgate.com/)
- [pfSense Docs](https://docs.netgate.com/pfsense/en/latest/index.html)
- [pfSense Firewall Docs](https://docs.netgate.com/pfsense/en/latest/firewall/index.html)
- [pfSense Configuration Docs](https://docs.netgate.com/pfsense/en/latest/config/)
- [UniFi Docs](https://help.ui.com/hc/en-us/categories/200320654-UniFi-Wireless)
- [UniFi Controller Versions](https://help.ui.com/hc/en-us/articles/360008240754#1)

## Let's Get Started

**1.** I recommend you use an [uninterruptible power supply](https://www.apc.com/shop/us/en/products/APC-Back-UPS-BE850M2-850VA-2-USB-charging-ports-120V/P-BE850M2) aka "UPS" for your pfSense setup. This will prevent problems that can happen due to sudden powerloss.

**2.** Get familiar with the Netgate SG-1100 using these videos below or other resources you prefer. I have included video dates to make users aware that some features that appear may have updated, changed, or look different in some way. Keep in mind the age of any video and do your own research!

- [Netgate pfSense SG 1100 Review & Speed Tests](https://youtu.be/_bM3XqK5JzE) - Feb 17, 2019 

- [The Netgate pfSense SG-1100 Still A Good Home Router? What About Gaming?](https://youtu.be/6VqeB5eXjq0) - Sep 13, 2019

**3.** You can also do a [DIY pfSense build](https://www.youtube.com/watch?v=9kSZ1oM-4ZM) if you have the proper hardware on hand and feel comfortable doing so. Also, take a look at the [Netgate SG-3100](https://www.youtube.com/watch?v=dbSUdDyfW0M) if you need something a little bit more powerful. There are plenty of options for average users, small biz, and more.

**4.** If you are new to networking stuff or need a refresher, then see the free courses from [Udemy](https://www.udemy.com/course/introduction-to-networking-for-complete-beginners/) or from [Edx](https://www.edx.org/course/introduction-to-networking). They are decently short and easy.

**5.** Now get familiar with pfSense, Networks, and Features. 

- [2020 Getting started with pfSense 2.4 Tutorial: Network Setup, VLANs, Features & Packages](https://www.youtube.com/watch?v=fsdm5uc_LsU) - Aug 7, 2020

**6.** If you prefer to have Wifi, as most will, then you need to setup VLANs. Thusly I recommend that you use [UniFi line of products by Ubiquiti](https://www.ui.com/products/#unifi). I love their products and so far have not had any major issues with them. You will need a network switch and perhaps a Wifi access point or two depending on your home. Here are some reccomendations. 

- [Ubiquiti - UniFi® Switch 8](https://www.ui.com/unifi-switching/unifi-switch-8/)

- [Ubiquiti - UniFi® AP AC PRO](https://www.ui.com/unifi/unifi-ap-ac-pro/)

**7.** Take a little more time to research and consider if you would like to have VLANs setup. This is very useful for putting junk IOT or Wifi devices that I do not trust on their own "crap network(s)". I **do not recommend** using Wifi on a secure setup unless you setup VLANs and restrict access using Pfsense firewall rules.

- [How To Setup VLANS With pfsense & UniFI + firewall rules for VLANS in pfSense](https://www.youtube.com/watch?v=b2w1Ywt081o) - Dec 18, 2017

- [Whate are Virtual LANs (VLANs)?](https://www.youtube.com/watch?v=dpoUjnfGbeo) - Dec 21, 2016

**8.** After setting up pfSense to your liking, it is time to get your UniFi products online and connected to their controller. I prefer to use a Raspberry Pi 3 or better to run a dedicated UniFi controller 24/7, rather than having the software on a desktop. It is ok to run the controller on a desktop for a little while of course, and you can simply swap to the Pi once ready.

- [Install Unifi Controller On Raspberry Pi](https://lazyadmin.nl/home-network/installing-unifi-controller-on-a-raspberry-pi-in-5-min/)

- [Updating Unifi Controller on Raspberry Pi](https://lazyadmin.nl/home-network/updating-unifi-controller-on-raspberry-pi/)

- [UniFi - How to Set Up a UniFi Network Controller](https://help.ui.com/hc/en-us/articles/360012282453-UniFi-How-to-Set-Up-a-UniFi-Network-Controller) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ,**<sup>Use advanced setup, and do not login to their servers!</sup>**

- [UniFi - How to Install and Update via APT on Debian or Ubuntu](https://help.ui.com/hc/en-us/articles/220066768-UniFi-How-to-Install-and-Update-via-APT-on-Debian-or-Ubuntu)

**TODO:** make unifi network controller setup script

**INFO:**
https://blog.ktz.me/how-to-adopt-a-unifi-ap-with-a-remote-controller/
