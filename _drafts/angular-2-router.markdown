---
layout:     post
title:      "Angular 2 - Router"
subtitle:   "Um manual de como utilizar o novo sistema de rotas do AngularJS"
date:       2015-03-21 13:00:00
author:     "Bruno Belarmino"
header-img: "img/post-bg-04.jpg"
#disqus-identifier: "2015-03-21-angular-2-router"
---

<p>Fala Amigos!</p>

<p>
	No post de hoje vamos falar um pouco sobre o novo sistema de rotas que está sendo preparado para a próxima versão do AngularJS.
</p>

<h4>Era uma vez</h4>

<p>
	Históricamente o angularjs desde a sua concepção já vinha com um sistema de rotas embutido conhecido como <em>ngRoute</em>. E como todos sabem este roteador tem algumas limitações, como por exemplo a criação de rotas embedadas ou simplesmente rotas filhas. E assim algum tempo se passou, novas alternativas independentes (que não são mantidas pelo próprio time do angularjs) surgiram como por exemplo o <em>Ui-Router</em> que é um sistema de rotas baseado em estados (diga-se de passagem muito bom!), mas o <em>ngRoute</em> continuou da mesma forma, sem grandes novidades e claro recebendo muita críticas e solicitações por parte de seus usuários. 
</p>

<p>
	Até que surge a necessidade de evolução do framework e o time do angularjs começa a trabalhar na sua nova versão. E no meio de uma reunião de escopo e design emerge o necessidade de evoluir (nesse caso especificamente reescrever) o sistema de rotas atual. E assim surge o <em>AngularJS New Router</em>. 
</p>

<h4>New Router</h4>

<p>
	O novo sistema de rotas do angular está num estágio bem evoluido de desenvolvimento e já é possivel testá-lo com o angular 1.4.
</p>

<p>
	Para realizar a instalação você pode usar o npm (gerenciador de pacotes do nodejs):
</p>

<code>
	npm install angular-new-router
</code>

<p>
	Ou simplesmente efetuar o download a partir do github do projeto:
</p>

<a href="https://github.com/angular/router/">https://github.com/angular/router</a>

<h4>Let's code</h4>

<p>
	Após o download das dependências vamos realizar a configuração de um projeto simples utilizando o <em>new router</em>: 
</p>