---
layout: post
title:  "SSH in Mac OS terminal"
ref: sshMacOSTerminal
date:   2016-06-16 07:03:44 -0300
lang: en
---

Hi


Today I've needed access an external ssh conection. I'm a new Mac OS user and what I need to do?

The first step I've installed the brew, and I opened the terminal and I've installed the putty.

{% highlight shell %}
brew install putty
{% endhighlight %}

The next, I've needed the pem file, when you wanna access the AWS EC2 Server, you need of the pem file. This file is generated from AWS Panel.

I have the ppk file, but the puttygen generates the pem file based on a ppk file.

{% highlight shell %}
puttygen myprivatekey.ppk -O private-openssh -o myprivatekey.pem
{% endhighlight %}

Great... now we have the pem file, let's connect.

{% highlight shell %}
ssh -i myprivatekey.pem myuser@myserver.com
{% endhighlight %}  

The last thing I wanna create the tunnel through my machine and ssh connection.

{% highlight shell %}
ssh -i myprivatekey.pem myuser@myserver.com -L:MyMachinePort:ExternalAddress:ExternalPort
{% endhighlight %}

Now if I wanna create too tunnels, I can add others -L parameters.

That's all!!!

Bye. 