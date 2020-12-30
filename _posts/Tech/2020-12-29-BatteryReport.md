---
layout: post
title: How to get the battery report from windows 10?
categories: Technology
description: Get a detailed battery report
keywords: Tech, battery, Windows10
---

1. Open the windows powershell admin

2. Copy and paste the powershell script:

```Powershell
    powercfg /batteryreport /output "C:\battery-report.html"
```

More details from here: [Powercfg command-line options](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/powercfg-command-line-options)