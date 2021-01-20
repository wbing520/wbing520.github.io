---
layout: post
title: Setup the Jupyter notebook 
categories: DS
description: setup the Jupyter notebook in WSL
keywords: DS, Python, Jupyter
---

## DS development Environment

In order to install a DS development environment, we have several solutions, like the Anaconda on the windows machine, using Virtual box with Linux Distro Mint with Anaconda, or using Google’s Colab platform. The Windows Subsystem for Linux (WSL) is also a great choose. Here are the steps to setup the DS development environment using WSL.

```
1)Check the windows version
     Windows + R to open the “Run” dialog.
     Enter “winver” to check the windows version.(OS version need to be 1903 or higher with build 18362 or higher)
My windows OS is Build 19041.746, good enough for the WSL.
2)Enable the Windows Subsystem for Linux and Enable virtual machine feature using the PowerShell.

a)dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
b)dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

3)Download the latest Linux kernel update package and install.
[WSL2 Linux kernel update package for x64 machines](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
4)Open the Microsoft Store and select what we need
Here I choose the Ubuntu 20.04 LTS. https://www.microsoft.com/en-us/p/ubuntu-2004-lts/9n6svws3rx71?rtc=1&activetab=pivot:overviewtab
5)After install the Ubuntu in WSL, if the disk is not big enough. We could move it to another disk. 

Export the distribution.
 	wsl.exe --export <DistributionName> <Tar-FileName>
Import the distribution into target folder
	wsl.exe --import <DistributionName> <Folder-To-Install> <Tar-FileName>

For example:
	Export: C:\> wsl.exe --export Ubuntu c:\data\ubuntu.tar
    Import: C:\> wsl.exe --import Ubuntu d:\wsl\Ubuntu c:\data\ubuntu.tar

6)Update the Linux environment
	a)sudo apt update
	b)sudo apt upgrade
7)Install the python and pip
	a)sudo apt install python3 python3-pip ipython3
8)Install Jupyter notebook
	a)pip3 install jupyter
9)Enter Jupyter-notebook and run the Jupyter-notebook server
10)Open the browser and access the http://localhost:8888, we could see the jupyter notebook password UI
11)Go back to command line and enter jupyter notebook password
to setup the password. 
12)Rerun the Jupyter-notebook and we could see it up and running like followings. 

Here are the pictures.

```
