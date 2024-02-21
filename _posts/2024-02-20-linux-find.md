---
layout: post
title:  "Linux - Find commands"
date:   2024-02-20 15:48:21 +0000
categories: linux
tags: find terminal
---
## Some resources for using the find command in linux terminal

fd find a good alternative
[https://github.com/sharkdp/fd](https://github.com/sharkdp/fd)

[some gist find examples](https://gist.github.com/gr1ev0us/3a9b9d9dbdd38f6379288eb2686fc538)

[35-practical-examples-of-linux-find-command](https://www.tecmint.com/35-practical-examples-of-linux-find-command/)

##### larger than
{% highlight bash %}
find . -type f -size +4G
{% endhighlight %}

{% highlight bash %}
find . -type f -size +4G
{% endhighlight %}

{% highlight bash %}
find /folder/docker-builds/ -type f -size +5M  -exec ls -l --block-size=M {} +
{% endhighlight %}

##### find read only file
{% highlight bash %}
find / -perm /u=r
{% endhighlight %}

##### Find all 777 permission files and use chmod command to set permissions to 644.
{% highlight bash %}
find / -type f -perm 0777 -print -exec chmod 644 {} \;
{% endhighlight %}

##### To find a single file called tecmint.txt and remove it.
{% highlight bash %}
find . -type f -name "tecmint.txt" -exec rm -f {} \;
{% endhighlight %}

##### To find all files that belong to user Tecmint under /home directory.
{% highlight bash %}
find /home -user tecmint
{% endhighlight %}

##### To find all the files which are accessed 50 days back.
{% highlight bash %}
find / -atime 50
{% endhighlight %}

##### To find all 50MB files, use.
{% highlight bash %}
find / -size 50M
{% endhighlight %}

##### Find all .mp3 files with more than 10MB and delete them using one single command.
{% highlight bash %}
find / -type f -name *.mp3 -size +10M -exec rm {} \;
{% endhighlight %}

##### Find all files in directory modified last 30 days
{% highlight bash %}
find . -maxdepth 1 -mtime +30 -printf "%T+\t%p\n" | sort
{% endhighlight %}

##### Find then grep
{% highlight bash %}
find . -name '*bills*' -exec grep -H "put" {} \;
{% endhighlight %}

##### find all extensions and rename
{% highlight bash %}
find . -name '*.js' -exec rename "s/js$/ts/" {} +
{% endhighlight %}

##### count files of type
{% highlight bash %}
find . -mindepth 1 -type f -name "*.js" -exec printf x \; | wc -c
{% endhighlight %}

##### lines in a directory
{% highlight bash %}
find ./src -type f -exec wc -l {} \; | awk '{total += $1} END{print total}'
{% endhighlight %}
