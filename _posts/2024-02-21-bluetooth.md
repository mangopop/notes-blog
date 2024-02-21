---
layout: post
title:  "Poor Bluetooth audio quality"
date:   2024-02-21 16:29:00 +0000
categories: windows
tags: bluetooth troubleshooting
---

If you're experiencing patchy Bluetooth audio quality with your headphones, running this command in PowerShell as an administrator will instantly restore the audio quality.

{% highlight powershell %}
Get-Service -DisplayName *Bluetooth* | Restart-Service -Force
{% endhighlight %}
