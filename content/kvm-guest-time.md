---
title: "KVM Windows Guest Time"
date: 2017-08-04
tags: []
categories:
  - Linux
  - KVM
  - Windows
draft: false
---

I recently converted my Windows 10 VM from Virtualbox to VKM. The time in the VM was getting out of sync.

I found this setting that resolved the issue for me.

~~~
To change the hardware clock in windows, you can add this registry entry :

[HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\TimeZoneInformation]
"RealTimeIsUniversal"=dword:00000001
~~~

But After updating to the Fall Creators Update I have noticed some time when the VM is suspended and resumed.
