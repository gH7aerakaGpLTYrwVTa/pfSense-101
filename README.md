# pfSense 101

# Table of Contents
* [**1. Introduction**](https://github.com/gH7aerakaGpLTYrwVTa/pfSense-101/blob/master/README.md#introduction)
* [**1. Main Documentation Sources**](https://github.com/gH7aerakaGpLTYrwVTa/pfSense-101/blob/master/README.md#main-documentation-sources)
* [**2. Preparation**](https://github.com/gH7aerakaGpLTYrwVTa/pfSense-101/blob/master/README.md#preparation)
* [**3. Get Familiar**](https://github.com/gH7aerakaGpLTYrwVTa/pfSense-101/blob/master/README.md#get-familiar) 
* [**4. Setup**](https://github.com/gH7aerakaGpLTYrwVTa/pfSense-101/blob/master/README.md#setup)
* [**5. Backups**](https://github.com/gH7aerakaGpLTYrwVTa/pfSense-101/blob/master/README.md#backups)

## Introduction

This repo is for information about pfSense, Netgate, Unifi, and other basics that a user may need to setup a secure home network. It geared towards users with an average skill level, and I will also assume that most want Wifi capability.

You will notice that I suggest hardware that may need to be purchased, but some of may be done with hardware you have on hand already. Power users may prefer to build their own solutions and take a different approach.

Some helpful scripts will be included in the repo if you wish to use them. There are a lot of videos in this guide, and if you do not like learning via video then you might want to look elsewhere. I think the average user will really enjoy how powerful this setup can be!

## Main Documentation Sources

- [Netgate Docs](https://docs.netgate.com/)
- [pfSense Docs](https://docs.netgate.com/pfsense/en/latest/index.html)
- [pfSense Firewall Docs](https://docs.netgate.com/pfsense/en/latest/firewall/index.html)
- [pfSense Configuration Docs](https://docs.netgate.com/pfsense/en/latest/config/)
- [UniFi Docs](https://help.ui.com/hc/en-us/categories/200320654-UniFi-Wireless)
- [UniFi Controller Versions](https://help.ui.com/hc/en-us/articles/360008240754#1)

## Preparation

I recommend you use an [uninterruptible power supply](https://www.apc.com/shop/us/en/products/APC-Back-UPS-BE850M2-850VA-2-USB-charging-ports-120V/P-BE850M2) aka "UPS" for your pfSense setup. This will prevent problems that can happen due to sudden powerloss.

Get familiar with the Netgate SG-1100 using these videos below or other resources you prefer. I have included video dates to make users aware that some features that appear may have updated, changed, or look different in some way. Keep in mind the age of any video and do your own research!

- [Netgate pfSense SG 1100 Review & Speed Tests](https://youtu.be/_bM3XqK5JzE) - Feb 17, 2019 

- [The Netgate pfSense SG-1100 Still A Good Home Router? What About Gaming?](https://youtu.be/6VqeB5eXjq0) - Sep 13, 2019

You can also do a [DIY pfSense build](https://www.youtube.com/watch?v=9kSZ1oM-4ZM) if you have the proper hardware on hand and feel comfortable doing so. Also, take a look at the [Netgate SG-3100](https://www.youtube.com/watch?v=dbSUdDyfW0M) if you need something a little bit more powerful. There are plenty of options for average users, small biz, and more.

If you are new to networking stuff or need a refresher, then see the free courses from [Udemy](https://www.udemy.com/course/introduction-to-networking-for-complete-beginners/) or from [Edx](https://www.edx.org/course/introduction-to-networking). They are decently short and easy.

## Get Familiar

Now is a good time to start becoming familiar with pfSense, VLANs, and many other features. 

- [2020 Getting started with pfSense 2.4 Tutorial: Network Setup, VLANs, Features & Packages](https://www.youtube.com/watch?v=fsdm5uc_LsU) - Aug 7, 2020

If you prefer to have Wifi, as most will, then you need to setup VLANs. Thusly I recommend that you use [UniFi line of products by Ubiquiti](https://www.ui.com/products/#unifi). I love their products and so far have not had any major issues with them. You will need a network switch and perhaps a Wifi access point or two depending on your home. Here are some reccomendations. 

- [Ubiquiti - UniFi® Switch 8](https://www.ui.com/unifi-switching/unifi-switch-8/)

- [Ubiquiti - UniFi® AP AC PRO](https://www.ui.com/unifi/unifi-ap-ac-pro/)

Take a little more time to research and consider if you would like to have VLANs setup. This is very useful for putting junk IOT or Wifi devices that I do not trust on their own "crap network(s)". I **do not recommend** using Wifi on a secure setup unless you setup VLANs and restrict access using Pfsense firewall rules.

- [How To Setup VLANS With pfsense & UniFI + firewall rules for VLANS in pfSense](https://www.youtube.com/watch?v=b2w1Ywt081o) - Dec 18, 2017

- [Whate are Virtual LANs (VLANs)?](https://www.youtube.com/watch?v=dpoUjnfGbeo) - Dec 21, 2016

## Setup

Go ahead and deploy your pfSense box, you deserve it after all that research! After setting up pfSense to your liking, it is time to get your UniFi products online and connected to their controller. I prefer to use a Raspberry Pi 3 or better to run a dedicated UniFi controller 24/7, rather than having the software on a desktop. It is ok to run the controller on a desktop for a little while of course, and you can simply swap to the Pi once ready.

- [Install Unifi Controller On Raspberry Pi](https://lazyadmin.nl/home-network/installing-unifi-controller-on-a-raspberry-pi-in-5-min/)

- [Updating Unifi Controller on Raspberry Pi](https://lazyadmin.nl/home-network/updating-unifi-controller-on-raspberry-pi/)

- [UniFi - Set Up a Network Controller](https://help.ui.com/hc/en-us/articles/360012282453-UniFi-How-to-Set-Up-a-UniFi-Network-Controller) &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ,**<sup>Use advanced setup, and do not login to their servers!</sup>**

- [UniFi - Install and Update via APT on Debian](https://help.ui.com/hc/en-us/articles/220066768-UniFi-How-to-Install-and-Update-via-APT-on-Debian-or-Ubuntu)

**TODO:** make unifi network controller setup script

Make sure to [adopt the new Unifi controller](https://blog.ktz.me/how-to-adopt-a-unifi-ap-with-a-remote-controller/) if you set it up on a Raspberry Pi. This is very important! Also, take a look at this info on how to [SSH remote login to your Unifi Switch or Wifi APs](https://help.ui.com/hc/en-us/articles/218850057-Intro-to-Networking-How-to-Establish-a-Connection-Using-SSH#4).

## Backups

**TODO:** show user how to backup or import backups 

https://docs.netgate.com/pfsense/en/latest/backup/index.html
https://docs.netgate.com/pfsense/en/latest/backup/autoconfigbackup.html#manually-backing-up

https://help.ui.com/hc/en-us/articles/204952144-UniFi-How-to-Create-and-Restore-a-Backup
https://help.ui.com/hc/en-us/articles/226218448-UniFi-How-to-Configure-Auto-Backup
https://help.ui.com/hc/en-us/articles/360012624134-UniFi-Troubleshooting-Issues-with-Controller-Backup-Files
