---
layout: post
title:  "Linux - Find commands"
date:   2024-02-20 15:48:21 +0000
categories: linux
tags: find terminal
---

{% highlight bash %}
find . -type f -size +4G
{% endhighlight %}

https://gist.github.com/gr1ev0us/3a9b9d9dbdd38f6379288eb2686fc538
https://www.tecmint.com/35-practical-examples-of-linux-find-command/ 

### larger than
`find . -type f -size +4G`

`find /folder/docker-builds/ -type f -size +5M  -exec ls -l --block-size=M {} +`

### find read only file
`find / -perm /u=r`

### Find all 777 permission files and use chmod command to set permissions to 644.
`find / -type f -perm 0777 -print -exec chmod 644 {} \;`

### To find a single file called tecmint.txt and remove it.
`find . -type f -name "tecmint.txt" -exec rm -f {} \;`

### To find all files that belong to user Tecmint under /home directory.
`find /home -user tecmint`

### To find all the files which are accessed 50 days back.
`find / -atime 50`

### To find all 50MB files, use.
`find / -size 50M`

### Find all .mp3 files with more than 10MB and delete them using one single command.
`find / -type f -name *.mp3 -size +10M -exec rm {} \;`

### Find all files in directory modified last 30 days
`find . -maxdepth 1 -mtime +30 -printf "%T+\t%p\n" | sort`

### Find then grep
`find . -name '*bills*' -exec grep -H "put" {} \;`

### find all extensions and rename
`find . -name '*.js' -exec rename "s/js$/ts/" {} +`

### count files of type
`find . -mindepth 1 -type f -name "*.js" -exec printf x \; | wc -c`

### lines in a directory
`find ./src -type f -exec wc -l {} \; | awk '{total += $1} END{print total}'`
