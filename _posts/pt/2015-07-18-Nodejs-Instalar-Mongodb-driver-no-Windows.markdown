---
layout: post
title:  "Node.js: Instalar MongoDb Driver no Windows"
subtitle:   "Incluindo um parâmetro para instalação do MongoDb Driver"
date:       2015-07-18 18:10:00
author:     "Luidy M. Naves"
disqus-identifier: "2015-07-18-Nodejs-Instalar-Mongodb-driver-no-Windows"
ref: nodejsmongodbnodegyp
lang: pt
image: /assets/article_images/2015-07-18-Nodejs-mongodb-driver-no-windows/IMG_20150921_120519223.jpg
---


Olá!

Nesse primeiro post darei uma dica de como instalar o MongoDb driver no Windows através do comando npm. O MongoDb driver serve para criar aplicações Node.js acessando um banco de dados MongoDb.


Utilizando Node.js e tentando instalar no Windows o MongoDb driver com o npm, o node-gyp solicita um compilador c++ para gerar nativamente os pacotes do mongodb driver.


Pra quem não sabe o que é o <a href="https://github.com/TooTallNate/node-gyp" target="_blank">node-gyp</a>, em resumo ele é uma ferramenta escrita em Node.js para compilar nativamente os módulos de um addon.


Voltando ao nosso caso, o node-gyp por padrão hoje procura pelo MSBuild do Visual Studio 2010 que contenha o Visual C++ para realizar a compilação c++ da qual ele necessita. Caso ele não encontre o compilador c++ vai ocorrer um erro parecido com o da imagem abaixo.


	
![Instalando MongoDb Driver](/assets/article_images/2015-07-18-Nodejs-mongodb-driver-no-windows/PostNodejsMongoDbDriver.png)
	


Legal, mas e caso tenha instalado o Visual Studio 2012 ou 2013 e não tenha o 2010, precisa instalar o VS 2010? Não, precisa apenas passar um parâmetro indicando a versão do Visual Studio instalada no momento da instalação do mongodb driver.


O parâmetro a ser enviado é o <em>--msvs_version={versão do visual stuio}</em>, vamos ver como ficaria caso tenha a versão 2013 instalada.

{% highlight shell %}
npm install --msvs_version=2013 mongodb
{% endhighlight %}


Simples, agora ficou fácil instalar o mongodb driver no windows através do comando npm.


Lembrando que para quem não tem nenhum Visual Studio pode baixar uma versão express qual é gratuita.

OBS.: Existe um sistema de fallback no Node.js que mesmo não executando a compilação nativa ele permite que o pacote seja utilizado. Lembrando que existem outros pacotes que também utilizam da mesma compilação.

Até a próxima!