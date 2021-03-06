---
title: IOT Link Windows 10 Lock Monitor
date: 2021-03-27 00:06:05
tags: home-automation
---

[IOT Link](https://iotlink.gitlab.io/) is a great tool for monitoring / controlling your Windows PC using MQTT. Among its many features is the ability to monitor processes, which can be used to detect whether or not the machine is locked (at least on Windows 10, which has a process called "LogonUI.exe" for the UI of the lock screen). Once you've got it installed and configured, the instructions below will guide you through setting up the process monitor to detect if the machine is locked. 

In subsequent posts, I'll explain how to integrate this with [Home Assistant](https://www.home-assistant.io/) to detect whether or not your Windows PC is locked. Then, with other neat things like a [particle_photon_pc_keyboard](https://github.com/nathanmfast/particle_photon_pc_keyboard), which allows you to unlock your Windows PC via MQTT, you can build home automations that do really cool things, like boot up and login to your computer and set the lighting automatically before meetings on your work calendar. 

# Instructions

Install [IOT Link](https://iotlink.gitlab.io/)

Navigate to `C:\ProgramData\IOTLink` or wherever you have IOT Link installed.

We'll be working within the `Addons\ProcessMonitor` subfolder. 

Download <a href="/files/IOT-Link-Windows-10-Lock-Monitor/LogonUI.yaml" download>LogonUI.yaml</a> and place in the `apps` subfolder.

In `addon.yaml`, enable the ProcessMonitor addon:
```
########################################################################
# Addon Information
########################################################################
enabled: true
id: ProcessMonitor
name: Process Monitor
file: ProcessMonitor.dll
minApiVersion: 2.2.0
maxApiVersion: 
```

In `config.yaml`, at the bottom, add this monitor:
```
monitors:
  LogonUI: !include apps/LogonUI.yaml
```