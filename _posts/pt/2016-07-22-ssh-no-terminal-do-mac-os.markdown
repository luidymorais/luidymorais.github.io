---
layout: post
title:  "SSH no terminal Mac OS"
ref: sshMacOSTerminal
date:   2016-07-22 07:03:44 -0300
image: /assets/article_images/2016-07-22-ssh-in-mac-os/home.jpg
lang: pt
---

Olá


Hoje eu precisei acessar uma conexão externa via ssh. Eu sou um novo usuário de Mac OS, o que fazer?

Primeiro instalar o brew, depois instalar o putty.

{% highlight shell %}
brew install putty
{% endhighlight %}

Precisei do arquivo pem para acessar o AWS EC2 Server. Esse arquivo é gerado no AWS Panel.

Tenho um arquivo ppk, então com o puttygen gerei o arquivo pem baseado no meu arquivo ppk.

{% highlight shell %}
puttygen myprivatekey.ppk -O private-openssh -o myprivatekey.pem
{% endhighlight %}

Legal... agora com o arquivo pem, vamos conectar.

{% highlight shell %}
ssh -i myprivatekey.pem myuser@myserver.com
{% endhighlight %}  

A última coisa a ser criada é o tunel entre minha máquina e a conexão ssh.

{% highlight shell %}
ssh -i myprivatekey.pem myuser@myserver.com -L:MyMachinePort:ExternalAddress:ExternalPort
{% endhighlight %}

Caso queira criar mais túneis, basta adicionar outro -L como parâmetro.

É isso... até a próxima!!!