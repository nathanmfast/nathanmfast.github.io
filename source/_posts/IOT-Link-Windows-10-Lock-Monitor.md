---
title: IOT Link Windows 10 Lock Monitor
date: 2021-03-27 00:06:05
tags:
---

<!-- ![Sample](sample.jpg)

[Post LogonUI.yaml](LogonUI.yaml){:target="_blank"}

[Files LogonUI.yaml](/files/IOT-Link-Windows-10-Lock-Monitor/LogonUI.yaml){:target="_blank"}

<%- link_to('/files/LogonUI.yaml', 'Google', {external: true}) %> 

<a href="/files/IOT-Link-Windows-10-Lock-Monitor/LogonUI.yaml" download>Download Files\IOT-Link-Windows-10-Lock-Monitor\LogonUI.yaml</a>

-->

Download: <a href="/files/IOT-Link-Windows-10-Lock-Monitor/LogonUI.yaml" download>LogonUI.yaml</a>

C:\ProgramData\IOTLink\Addons\ProcessMonitor

addon.yaml
enable this addon
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


config.yaml
at the bottom, add this monitor
```
monitors:
  LogonUI: !include apps/LogonUI.yaml
```