---
layout: post
title:  "Testando APIs Restful com Chakram JS"
ref: testandoAPIRestChakram
date:   2016-11-09 07:03:44 -0300
lang: pt
---

Recentemente estava procurando uma solução javascript/node.js para realizar os testes de APIs Restful. 

Me deparei com um framework chamado Chakram que facilita os testes de APIs.

Para criar um projeto usando Chakram é necessário ter o node.js instalado, aconselho usar o NVM (Node Version Manager) para instalar e gerenciar as versões do node.js.

Abaixo segue os links para instalação do NVM:

Windows

* [https://github.com/coreybutler/nvm-windows](https://github.com/coreybutler/nvm-windows){:target="_blank"}

Linux / MacOS

* [https://github.com/creationix/nvm](https://github.com/creationix/nvm){:target="_blank"}


Sugestão para quem utiliza Windows é instalar o conemu que é um terminal mais amigável que o tradicional do windows, principalmente para quem não usa windows 10, abaixo o link para download:

* [https://sourceforge.net/projects/conemu/](https://sourceforge.net/projects/conemu/){:target="_blank"}


Após intalado o nvm instale a versão LTS mais recente do node.js via nvm, um comando como:

{% highlight shell %}
nvm install [VERSÃO_LTS_DO_NODE]
{% endhighlight %}

O próximo passo é criar um projeto Node.js crie um diretório chamado testeAPI e dentro desse diretório, via linha de comando execute:

{% highlight shell %}
npm init -y
{% endhighlight %}

O comando acima irá criar um arquivo chamado package.json, nesse arquivo contém uma série de informações com relação ao gerenciamento de pacotes npm. Mais informações [https://docs.npmjs.com/files/package.json](https://docs.npmjs.com/files/package.json){:target="_blank"}.

Instalando o Chakram js:

{% highlight shell %}
npm install --save-dev chakram
{% endhighlight %}

Para rodar os testes será necessário instalar o mocha js:

{% highlight shell %}
npm install --save-dev mocha
{% endhighlight %}

Na documentação do Chakram JS e até mesmo do Mocha JS indica instalar o Mocha JS como um módulo global qual tem uma CLI para a execução dos testes, o que pode ser um problema ao longo do tempo por nem todos projetos estarem usando a mesma versão da CLI.

Crie no diretório um arquivo chamado zipTest.js. Vamos fazer uma chamada de uma API pública para consulta de cep do site ViaCEP ( [https://viacep.com.br/](https://viacep.com.br/){:target="_blank"} ).

{% highlight javascript linenos %}
'use strict';
var chakram = require('chakram'),
    expect = chakram.expect;


describe('Zipcode Test', function() {

    it('Give a Zipcode must return the name of city', function() {
        var zipcode = '37170000'

        return chakram.get('https://viacep.com.br/ws/' + zipcode + '/json/')
            .then(function(response) {

            
                expect(response).to.have.status(200);
                expect(response.body.localidade).to.equal('Boa Esperança');
        });
    });
});
{% endhighlight %}


Acima na linha 2 é importado o módulo do chakram e abaixo na linha 3 é importado o módulo de assertion do Chai JS que funciona em conjunto com o Mocha JS.

Na linha 6 é a descrição geral dos testes que estarão aninhados naquele bloco de código.

De fato na linha 8 é que começa o real teste que irá ser feito, onde dado um cep que conhecemos tem que retornar a cidade esperada.

Na linha 11 é chamada a API passando na própria url o cep que queremos consultar. Então na linha 12 temos o aguardo de uma promise para pegarmos o retorno da chamada à API.

Na linha 15 verificamos se a API conseguiu nos responder com sucesso aguardando um retorno 200 da chamada HTTP.

Para finalizar na linha 16 verificamos se o retorno do campo localidade é igual a cidade de Boa Esperança, já que passamos o cep 37170000 como parâmetro.

Verificando se o teste criado está funcionando rode o seguinte código na linha de comando:

{% highlight shell %}
node_modules/mocha/bin/mocha zipTest.js
{% endhighlight %}

OBS.: Caso estiver usando windows inverter as barras do caminho para o mocha.

Nesse post mostrei como iniciar os testes usando o Chakram Js, no próximo abordarei uma estrutura de como montar esses testes usando arquivos de configuração e reaproveitando várias chamadas de API.

Abaixo segue as referências assim como o link do código exemplificado acima:

* [https://github.com/luidynaves/testAPI](https://github.com/luidynaves/testAPI){:target="_blank"}
* [https://github.com/coreybutler/nvm-windows](https://github.com/coreybutler/nvm-windows){:target="_blank"}
* [https://github.com/creationix/nvm](https://github.com/creationix/nvm){:target="_blank"}
* [https://sourceforge.net/projects/conemu/](https://sourceforge.net/projects/conemu/){:target="_blank"}
* [https://docs.npmjs.com/files/package.json](https://docs.npmjs.com/files/package.json){:target="_blank"}
* [http://dareid.github.io/chakram/](http://dareid.github.io/chakram/){:target="_blank"}
* [http://chaijs.com/](http://chaijs.com/){:target="_blank"}
* [https://mochajs.org/](https://mochajs.org/){:target="_blank"}


Link para aprender um pouco de Node.js: [https://blog.risingstack.com/node-hero-tutorial-getting-started-with-node-js/](https://blog.risingstack.com/node-hero-tutorial-getting-started-with-node-js/){:target="_blank"}