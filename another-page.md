---
layout: default
title: Create VM in HyperV Powershell
description: This is just another page
---

## Create Virtual switch


	 Get-NetAdapter 
	 New-VMSwitch –Name “External VM Switch” –AllowManagement $True –NetAdapterName “Local Area Connection” 
	 Get-VMSwitch 


## Create VM

	New-VM -Name server2019 -path C:\vm-machine -MemoryStartupBytes 8000MB 

## Create new vhd

	New-VHD -Path c:\vm-Machine\Testmahcine\Testmachine.vhdx -SizeBytes 10GB -Dynamic 
## Map ISO image	
	Set-VMDvdDrive -server2019 -ControllerNumber 1 -Path 					

## ----------------------------------------------*OR*--------------------------------------------

## Use existing VHD

	Add-VMHardDiskDrive -VMName server2019 start vm-path "C:\hyperv\vhd\VHDfile.vhd" 		

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
