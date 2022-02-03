---
layout: default
title: Samba with SMB3
description: Install Samba on Ubuntu server
---

## Install Samba
	sudo apt update
	sudo apt install samba

## Make Shared Directory
	mkdir /home/*USERNAME*/sambashare/

## Configure Samba
	sudo nano /etc/samba/smb.conf
	
## ---------------At the bottom of the file, add the following lines:	**CHANGE *USERNAME

	
	[sambashare]
    comment = Samba on Ubuntu
    path = /home/*USERNAME*/sambashare				 
    read only = no
    browsable = yes

## Restart service
	
	sudo service smbd restart

## enable Samba through firewall
	sudo ufw allow samba

## Create Samba User
	sudo smbpasswd -a *USERNAME*

## Enable SMB3 Protocol
	protocol = SMB3



[back](./)
