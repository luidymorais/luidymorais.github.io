---
layout:     post
title:      "Collections ES6 parte 1"
date:       2015-03-15 16:30:00
author:     "Bruno Belarmino"
header-img: "img/post-bg-02.jpg"
disqus-identifier: "2015-03-15-collections-es6-parte1"
---

<p>Fala Amigos!</p>

<p>
	Dando continuidade a nossa série sobre as novidades do Javascript, vamos falar hoje sobre collections.
</p>

<h4>Sets e Maps</h4>

<p>
	Historicamente a única collection que vinha por padrão no Javascript era o <em>Array</em>. Mas a partir do ES6 temos novos tipos como: <em>Set</em>, <em>WeakSet</em>, <em>Map</em> e <em>WeakMap</em>.  
</p>

<h4>Set</h4>

<p>
	Para quem tem conhecimento em linguagens de programação como C#, Java, Ruby e Python esta collection não é uma novidade, mas para quem tem conhecimento somente em Javascript, sim. Sendo assim, segue a definição:
</p>

<p>
	<em>Set</em> é um tipo de collection que permite a inserção de qualquer tipo de valor (Ex: objeto, function, número, string, etc) e não permite valores duplicados. Outra particularidade é que utilizando <em>Set</em> não é possível acessar um valor diretamente como é feito com <em>Array</em>, normalmente você valida para ver se o valor está presente ou itera sobre os valores.
</p>

<p>
	Um exemplo de uso para <em>Sets</em> é uma lista de pedidos onde cada pedido do usuário deve ser único e ocasionalmente é necessário verificar se aquele pedido já esta incluso.
</p>

<p>Simples!? Vamos ver na prática a utilização do <em>Set</em>:</p>

<pre>
	<code>
		//inicialização de um Set
		var set = new Set(); //cria um novo Set vazio
		var set2 = new Set([1, 2, 3]); //cria um novo Set a partir de um Array

		set.add(1); //adiciona um valor

		//número de valores no set
		set.size; // 1
		set2.size; // 3

		//verifica se o valor existe dentro do Set
		set.has(1); // true

		set.add(1); //adiciona um valor duplicado e nada acontece

		set.size; // 1

		set.delete(1); //remove um determinado valor do Set

		set.has(1); // false
		set.size; // 0

		//itera sobre os valores do Set
		for (let valor of set2) {
		  console.log(valor);
		}

		//itera sobre os valores do Set
		set2.forEach(function(valor) {
		  console.log(valor); 
		});

		//output das iterações: 
		// 1
		// 2
		// 3

		set2.clear(); //remove todos os valores do Set
		set2.size; // 0
	</code>
</pre>

<br/>
<h4>WeakSet</h4>

<p>
	É um <em>Set</em> que não previne que seus elementos/valores sejam coletados pelo garbage collector do Javascript.
	Além disso a sua api também é reduzida. Deste modo, não é permitido iterar sobre os valores do <em>Set</em> e/ou limpar os mesmos usando o método <em>clear</em>.
</p>

<p>
	Na prática, caso você utilize um objeto como valor do seu <em>WeakSet</em> e o mesmo não estiver sendo usado em mais nenhum lugar na sua aplicação, o garbage collector poderá limpar a sua referência e com isso magicamente o valor deixaria de existir.
</p>

<p>
	A api do <em>WeakSet</em> é composta de apenas 3 métodos quais funcionam da mesma forma que o <em>Set</em>:
</p>

<ul>
	<li>add(valor)</li>
	<li>has(valor)</li>
	<li>delete(valor)</li>
</ul>

<p>
	Até a próxima!
</p>

<script type="text/javascript">
var disqus_identifier = "2015-03-15-collections-es6-parte1";
var disqus_title = 'Collections ES6 parte 1';
</script>

{% include comments.html %}