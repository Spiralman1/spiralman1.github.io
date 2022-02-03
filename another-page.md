---
layout: default
title: Another page
description: This is just another page
---

## Create Virtual switch


Get-NetAdapter
New-VMSwitch –Name “External VM Switch” –AllowManagement $True –NetAdapterName “Local Area Connection”
Get-VMSwitch
---------------------------------------

#create VM

New-VM -Name server2019 -path C:\vm-machine -MemoryStartupBytes 8000MB

# New-VHD -Path c:\vm-Machine\Testmahcine\Testmachine.vhdx -SizeBytes 10GB -Dynamic 	#create new vhd
# Set-VMDvdDrive -server2019 -ControllerNumber 1 -Path					#map ISO image

				*OR*

Add-VMHardDiskDrive -VMName server2019 start vm-path "C:\hyperv\vhd\VHDfile.vhd" 		#use existing VHD

start-vm server2019

get-vm *

Get-VMNetworkAdapter -VMName Server2019

Get-VM "server2019" | Get-VMNetworkAdapter | Connect-VMNetworkAdapter -SwitchName "extenal switch name"		# assign virtual switch

get-vmswitch | select *

get-vm -n server2019 | Select -ExpandProperty NetWorkAdapters

#get-vm | ?{$_.State -eq "Running"} | select -ExpandProperty networkadapters | select vmname, macaddress, switchname, ipaddresses | ft -wrap -autosize						#View info for all VM adapters**


# Set-VMhost -EnableEnhancedSessionMode $True						#Enable Enhanced Session Mode 

# Enable-PSRemoting 									#enable remote management from hyperv gui


[back](./)
