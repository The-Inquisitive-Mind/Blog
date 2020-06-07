---
layout: post
title: "Reading email logs with Python"
description: "Program for interpreting linux email log file using python for various combinations"
categories: [Python]
tags: [python, file interpreter]
redirect_from:
  - /2020/06/07/
---

### Problem Statement
Program takes Linux email log file as input and interpret based on occurances and text filtering as similar to `awk`.
In following example, we're identifying sender [email] who has sent maximum number of emails. 

~~~ python
name = input("Enter file:")
if len(name) < 1 :
    name = "mbox-short.txt"
file = open(name)

bigword = None
bigcount = None
count = dict()

for line in file:
    if line.startswith('From '):
        line = line.split()
        # Following line set key of the dictionary as email id (from index position 1) and value as 0 if first occurance or increment count if count is not 0
        count[line[1]] = count.get(line[1], 0) + 1

for key,value in count.items():
    if bigword is None or value > bigcount:
        bigword = key
        bigcount = value

print('Sender',bigword,'who has sent maximum mails for',bigcount,'times')

~~~

### Example log file:
{% highlight javascript linenos=table %}
From stephen.marquard@uct.ac.za Sat Jan  5 09:14:16 2008
Return-Path: <postmaster@collab.sakaiproject.org>
------------------------------
From louis@media.berkeley.edu Fri Jan  4 18:10:48 2008

{% endhighlight %}


### Corresponding video here
<iframe width="600" height="415" src="https://www.youtube.com/embed/ypztpBvEe8k" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Execution:
![execution1](/blog/images/python_execution_20200607.jpg)


