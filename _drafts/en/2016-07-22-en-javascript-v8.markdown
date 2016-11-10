---
layout: post
title:  "Javascript V8"
ref: jsV8
date:   2016-07-22 07:03:44 -0300
lang: en
---


I've studied a little bit of node.js and I had an opportunity to understand how the javascript works in server.

Indeed, the javascript needs an engine to works in server. Under the Google Chrome Web Browser we need this structure.

Google created the V8 engine to supply every javascript which Chrome executes.

With C++ the V8 was created, logically the C++ language is some of the languages which you can reach an excellent performance.

The javascript code is converted to machine code by V8 engine. Wow... are you saying me the javascript code it transformed to machine code? Really? Sure.

So, when I put on the title "Javascript V8" is it not about javascript version? No, it's about V8 Engine.

The node.js is totally dependent of V8, but in this article I'm going to present how the V8 executes some codes with his samples.

I fetched the V8 source code and compiled it. 