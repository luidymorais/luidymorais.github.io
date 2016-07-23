---
layout: post
title:  "SSH in Mac OS terminal"
ref: sshMacOSTerminal
date:   2016-07-22 07:03:44 -0300
lang: en
---

Hi


Today I needed access an external ssh connection. I'm a new Mac OS user and what do I need to do?

The first step was install the brew then, I opened the terminal and installed the putty.

{% highlight shell %}
brew install putty
{% endhighlight %}

Next, I needed the pem file because when you wanna access the AWS EC2 Server, you need it. This file is generated from the AWS Panel.

I have the ppk file, but the puttygen generates the pem file based on a ppk file.

{% highlight shell %}
puttygen myprivatekey.ppk -O private-openssh -o myprivatekey.pem
{% endhighlight %}

Great... now we have the pem file, let's connect.

{% highlight shell %}
ssh -i myprivatekey.pem myuser@myserver.com
{% endhighlight %}  

The last thing I wanna create is the tunnel through my machine and ssh connection.

{% highlight shell %}
ssh -i myprivatekey.pem myuser@myserver.com -L:MyMachinePort:ExternalAddress:ExternalPort
{% endhighlight %}

Now if I also wanna create tunnels, I can add other -L parameters.

That's all!!!

Bye. 