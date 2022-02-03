---
layout: default
title: GUI on Ubuntu Server
description: Install GUI on Ubuntu Server
---

## Install Tasksel
	sudo apt-get update && sudo apt-get upgrade
	sudo apt-get install tasksel
	
## Install Slim or LightDM Display Manager 
	sudo apt-get install slim
	sudo apt-get install lightdm

## ---------------------ENVIRONMENTS--------------------------

## Install Gnome
	tasksel

## Install KDE PLasma
	sudo apt-get install kde-plasma-desktop
	sudo service display_manager start

## Install Mate Core Server Desktop
	sudo tasksel install ubuntu-mate-core
	sudo service display_manager start

## Install Lubuntu Core Server
	sudo tasksel install lubuntu-core
	sudo service display_manager start

## Install Xubuntu Server Core
	sudo tasksel install xubuntu-core
	sudo service display_manager start

##Install XFCE Desktop
	sudo apt-get install xfce4 slim
	sudo service slim start

## Switch Between GUIS By Pressing F1 At Login Screen


_yay_

[back](./)
