---
layout: page
title:  "Node.js: Instalar MongoDb Driver no Windows"
subtitle:   "Incluindo um parâmetro para instalação do MongoDb Driver"
date:       2015-06-07 10:30:00
author:     "Luidy M. Naves"
disqus-identifier: "2015-06-07-Nodejs-Instalar-Mongodb-driver-no-Windows"
---


{% include post-share.html %}

<article>
<p>Olá!</p>


<p>Nesse primeiro post darei uma dica de como instalar o MongoDb driver no Windows através do comando npm. O MongoDb driver serve para criar aplicações Node.js acessando um banco de dados MongoDb.</p>


<p>Utilizando Node.js e tentando instalar no Windows o MongoDb driver com o npm, o node-gyp solicita um compilador c++ para gerar nativamente os pacotes do mongodb driver.</p>


<p>Pra quem não sabe o que é o <a href="https://github.com/TooTallNate/node-gyp" target="_blank">node-gyp</a>, em resumo ele é uma ferramenta escrita em Node.js para compilar nativamente os módulos de um addon.</p>


<p>Voltando ao nosso caso, o node-gyp por padrão hoje procura pelo MSBuild do Visual Studio 2010 que contenha o Visual C++ para realizar a compilação c++ da qual ele necessita. Caso ele não encontre o compilador c++ vai ocorrer um erro parecido com o da imagem abaixo.</p>

<p>
	<a href="{{ site.baseurl }}/img/PostNodejsMongoDbDriver.png" target="_blank" alt="Clique na imagem para vê-la em tamanho real">
		<img src="../../../../img/PostNodejsMongoDbDriver.png" width="1000em" height="300em" >
	</a>
</p>

<p>Legal, mas e caso tenha instalado o Visual Studio 2012 ou 2013 e não tenha o 2010, precisa instalar o VS 2010? Não, precisa apenas passar um parâmetro indicando a versão do Visual Studio instalada no momento da instalação do mongodb driver.</p>


<p>O parâmetro a ser enviado é o <em>--msvs_version={versão do visual stuio}</em>, vamos ver como ficaria caso tenha a versão 2013 instalada.</p>

<pre>
<code>
	npm install --msvs_version=2013 mongodb
</code>
</pre>


<p>Simples, agora ficou fácil instalar o mongodb driver no windows através do comando npm.</p>


<p>Lembrando que para quem não tem nenhum Visual Studio pode baixar uma versão express qual é gratuita.</p>


<p>Até a próxima!</p>
</article>

{% include post-share.html %}


<div class="blog-comments">
<script type="text/javascript">
var disqus_identifier = "2015-06-07-Nodejs-Instalar-Mongodb-driver-no-Windows";
var disqus_title = 'Node.js: Instalar MongoDb Driver no Windows';
</script>

{% include comments.html %}
</div>