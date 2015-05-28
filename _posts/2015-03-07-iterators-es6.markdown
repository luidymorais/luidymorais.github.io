---
layout:     post
title:      "Iterators ES6"
date:       2015-03-07 13:50:00
author:     "Bruno Belarmino"
header-img: "img/post-bg-05.jpg"
disqus-identifier: "2015-03-07-iterators-es6"
---

<p>Fala amigos!</p>

<p>
	A partir de hoje iniciaremos uma série de posts falando sobre as novidades da nova versão do Javascript, conhecida como ES6 (EcmaScript 6). Que esta recheada de novidades e contemplando features muito legais como você verá na série.
</p>

<p>
	Como post de abertura vou falar hoje sobre iterators.
</p>

<h4>O que são?</h4>

<p>
	Iterator é um objeto com uma determinada interface. E essa interface consiste de um método chamado <em>next()</em> que retorna um objeto como resultado.
	
</p>
<p>
	Esse objeto de resultado, tem duas propriedades <em>value</em> referente ao valor corrente e <em>done</em> que é um valor booleano qual é setado para <em>true</em> quando não existem mais valores para serem retornados.
</p>
<p>
	O iterator mantém uma referência à posição correta do próximo valor dentro da coleção de valores. Deste modo, toda vez que o método <em>next()</em> é chamado ele retorna o valor correto. Caso o método <em>next()</em> for chamado após o último valor ser retornado o iterator irá retornar o objeto de resultado com os seguintes valores:
	<em>done</em> = <em>true</em> e <em>value</em> = <em>undefined</em>.
</p>

<h4>Show me the code!</h4>

<p>
	Com esse entendimento vamos ver na prática a implementação de um iterator:
</p>
<pre>
<code>
	var criarIterator = function(items){
		var i = 0;

		return {
			next: function(){

				var done = (i>= items.length);
				var value = !done ? items[i++] : undefined;

				return {
					done: done,
					value: value
				};
			}
		}
	};

	var iterator = criarIterator([1, 2, 3]);

	console.log(iterator.next());  // "{ value: 1, done: false}"
	console.log(iterator.next());  // "{ value: 2, done: false}"
	console.log(iterator.next());  // "{ value: 3, done: false}"
	console.log(iterator.next());  // "{ value: undefined, done: true}"
</code>
</pre>

<p>
	Simples neh!?
	<br/>
	Imagino que se você tenha conhecimentos em Java ou C# já tenha se perguntado, será? E a resposta é sim! Iterator em Javascript funciona de uma maneira bem semelhante ao iterator dessas linguagens.
</p>

<h4>Legal! Mas e onde eu uso isso?</h4>

<p>
	Iterator é uma peça fundamental na nova forma de manipular coleções de dados no ES6. Sendo assim todos os tipos de coleções (<em>Arrays</em>, <em>Sets</em>, <em>Maps</em> e até mesmo <em>Strings</em>) já vem com essa interface implementada. Liberando novas formas de interação com esses objetos.
</p>
<p>
	Além disso um bom entendimento sobre iterators irá te dar uma base sólida e te ajudar muito no entendimento de outras features do ES6. Assim como <em>collections</em>, <em>for of</em> e <em>generators</em> que serão assuntos dos próximos posts da série.  
</p>
<p>
	Até a próxima!
</p>

<script type="text/javascript">
var disqus_identifier = "2015-03-07-iterators-es6";
var disqus_title = 'Iterators ES6';
</script>

{% include comments.html %}