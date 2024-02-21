---
layout: post
title:  "Bluetooth quality poor"
date:   2024-02-21 16:29:00 +0000
categories: windows
tags: bluetooth troubleshooting
---

If headphones bluetooth audio quality really patchy, run this and it restores the quality instantly

{% highlight powershell %}
Get-Service -DisplayName *Bluetooth* | Restart-Service -Force
{% endhighlight %}