---
layout: post
title:  "Node.js: C++ node-gyp's dependency"
ref: nodejsmongodbnodegyp
date:   2016-07-12 07:03:44 -0300
lang: en
image: /assets/article_images/2015-07-18-Nodejs-mongodb-driver-no-windows/IMG_20150921_120519223.jpg
---

Hi


I wrote a similar post in Portuguese last year. I guess this trick is useful.

I was taking a course about MongoDB with Node.js at MongoDB Univerity and I needed to install the MongoDB driver in Windows. So, I came across node-gyp's problem because the MongoDB driver needs to compile natively.

Node-gyp is a Node.js tool to compile natively the addon modules. The node-gyp usually executes the C++'s MSBuild to compile the MongoDB driver.

Sometimes node-gyp doesn't find the C++ compiler, so we need to put a msvs_version parameter in a npm command line to install it.

{% highlight shell %}
npm install --msvs_version=2013 mongodb
{% endhighlight %}

Almost all add-ons have a fallback installation, instead of compiling natively they can run like a javascript library.

See ya...