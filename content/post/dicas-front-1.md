+++
date = "2017-06-08T15:00:00-03:00"
comments = true
title = "Dicas de Front-End #1"
slug = ""
tags = ["Dicas", "FrontEnd"]
author = "[Douglas Julião - DJ](https://github.com/dougjuliao)"
menu = "FrontEnd"
description = "Algumas dicas úteis no desenvolvimento front-end"
draft = false
share = true
image = "/images/dica-front-1.svg"
+++

### Introdução

Em minha experiência jà vi muitas coisas muito boas e também muito ruíns quando se diz respeito ao front-end,
existem pessoas que parecem que estão fazendo uma pintura enquanto estão codando mas também tem muitas pessoas que transforma o código em uma verdadeira zona,
o que eu quero dizer é, existem detalhes que podem ser pequenos mas que com uma vasta quantidade de código pode nos ajudar a ter um código mais legível e bem estruturado,
então criei um tipo de série com coisas que podem nos ajudar a melhorar o código ~~front-end.~~

### Html
Então vamos começar do ~~começo~~ nosso esqueleto o nosso [HyperText Markup Language](https://pt.wikipedia.org/wiki/HTML).

* Utilize o ``` <meta charset="UTF-8"> ``` - Para evitar problemas de acentuação e caracteres específicos.

* Além do meta charset existem outras meta tags que são muito boa para adicionar informações a mais para seu html,
normalmente utilizo meta author e description.
* Quando trabalhar com design responsivo utilize o meta viewport ``` <meta name="viewport" content="width=device-width, initial-scale=1.0">``` - Sem isso o site é tratado como apenas uma página web pequena
e não se adequará certo.
* Nunca esqueça de indentar seu código, nunca mesmo.
* Tente seguir as regras de semantica de uma estrutura padrão de html isso pode ser visto [aqui - w3c](https://www.w3.org/TR/html5/).
* Nunca repita um mesmo id.
* Utilize quantas classes forem necessárias mas tenha bom senso na nomenclatura - Existe duas visões nesse ponto, quando utilizamos nomenclatura de classe com o sentido real do conteúdo
nós temos uma leve melhora em nosso [SEO](http://www.seomaster.com.br/blog/o-que-e-seo) da página mas existem muitos sites por ai que utilizam a classe como várias siglas estranhas,
mas a questão é utilize nomes claros pois isso facilita muito para todos entenderem o código.
* Padronize o id e class - Por favor, não saia por ai utilizando CamelCase, dash-case e underscore_case igual um lunático é muito mais fácil criar uma separação das coisas, claro exitem patterns sobre essas nomenclaturas, mas
aqui será um gosto próprio, tente fazer assim:

    *para id utilize sempre underscore e evite utilizar letras maiúsculas.*<br />
    ``` <div id="meu_super_id"></div> ```

    *para class utilize sempre dash e tente criar até três nomes entre os traços.*<br />
    ``` <div class="minha-super-class"></div> ```


* Siga sempre a mesma ordem quando adicionar os atributos em suas tags:

    *Siga sempre essa ordem e logo após adicione os outros atributos dependendo da tag utilizada como por exemplo um input:*<br />
    ```<input id="" class="" data-input="" name="" placeholder="" value="">``` , *o importante é seguir sempre um padrão*.

    *É mais fácil vizualizar isso:*
    ```<div id="primeiro_id" class="segundo-class" data-atributo="terceiro-data-atributte">```
    ```<div id="primeiro_id" class="segundo-class" data-atributo="terceiro-data-atributte">```
    ```<div id="primeiro_id" class="segundo-class" data-atributo="terceiro-data-atributte">```

    *Do que visualizar isso:*
    ```<div id="primeiro_id" class="segundo-class" data-atributo="terceiro-data-atributte">```
    ```<div id="primeiro_id" data-atributo="terceiro-data-atributte" class="segundo-class">```
    ```<div data-atributo="terceiro-data-atributte" id="primeiro_id" class="segundo-class">```

    *Sempre siga padrões, se você decide começar de um jeito, termine ele do mesmo jeito que você o começou.*
* Chame sempre seu arquivo **.css** no topo da página logo após a tag **title**
* Chame sempre seu arquivo **.js** no fim da página dantes do fechamento da tag **body**

### Css
O famoso [Cascading Style Sheet](https://pt.wikipedia.org/wiki/Cascading_Style_Sheets), é também muito complicado de deixar bem estruturado.

* Como abordei acima - mantenha padrões.

* Tente seguir a estrutura do css de acordo com a estrutura do html - siga por heranças e de cima para baixo:

    *Por exemplo é bem melhor utilizar isso:*<br>
    ```body{}```<br />

    ```.header{}```<br />
    ```.header .menu{}```<br />

    ```.section{}```<br />
    ```.section .text{}```<br />

    ```.footer{}```<br />
    ```.footer .copyright{}```<br />

    *Do que utilizar isso:*

    ```.header{}```<br />
    ```.footer .copyright{}```<br />
    ```body{}```<br />
    ```.footer{}```<br />
    ```.section .text{}```<br />
    ```.header .menu{}```<br />
    ```.section{}```<br />

    *Pequenos detalhes fazem muita diferença.*<br />
* Tente utilizar até o máximo de três itens para definir estilo a um elemento:

    *Faça isso:*<br />
    ```.header .navigation .menu{}```<br />
    ```.menu .menu-li{}```<br />
    ```.menu .menu-li .menu-a{}```<br />
    *Ou apenas isso:*<br />
    ```.menu{}```<br />
    ```.menu-li{}```<br />
    ```.menu-a{}```<br />

    *Evite fazer isso:*<br />
    ```html body .container .header .navigation .menu{}```<br />
    ```html body .container .header .navigation .menu .menu-li{}```<br />
    ```html body .container .header .navigation .menu .menu-li .menu-a{}```<br />
    *Sério, evite isso, ou qualquer coisa parecida.*

* Quando aplicar estilo a mais de um seletor sempre de uma quebra de linha

    *Faça assim:*<br />
    ```.item-1,```<br />
    ```.item-2,```<br />
    ```.item-3,```<br />
    ```.item-4{```<br />
    ```display:block;```<br />
    ```width:100%;```<br />
    ```}```<br />

    *Evite isso, dependendo das classes utilizadas, se torna uma grande bagunça:*
    ```.item-1,.item-2,.item-3,.item-4{```<br />
    ```    display:block;```<br />
    ```    width:100%;```<br />
    ```}```<br />

* Quando existe apenas um estilo aplicado, deixe o mesmo sem quebra de linha:
    ```.item{ display:block; }```
* Evite ficar utilizando o !important, na maioria das vezes quando utilizamos isso é porque estruturamos o css de maneira errada.
### Javascript | jQuery
Utilizado para criar mágica em nossas páginas, aqui está o [Javascript](https://pt.wikipedia.org/wiki/JavaScript) e sua lib mais conhecida [jQuery](https://jquery.com/).
* Siga sempre um padrão de camelCase sempre quando precisar utilizar mais de um nome para determinada, variavel, funcão, classe ou o que for.
* Tente ao máximo não repetir o código.
* Declarar váriáveis (var,let,const) - apenas uma vez:

    *É mais performático utilizar assim:*<br />
    ```var a = "a",```<br />
    ```    b = "b",```<br />
    ```    c = "c",```<br />
    ```    d = "d";```<br />

    ```let a = "a",```<br />
    ```    b = "b",```<br />
    ```    c = "c",```<br />
    ```    d = "d";```<br />

    ```const a = "a",```<br />
    ```    b = "b",```<br />
    ```    c = "c",```<br />
    ```    d = "d";```<br />
    *Ou até mesmo assim:*<br />
    ```var a = "a", b = "b", c = "c", d = "d";```<br />
    ```let a = "a", b = "b", c = "c", d = "d";```<br />
    ```const a = "a", b = "b", c = "c", d = "d";```<br />

    *É melhor do que fazer isso:*<br />
    ```var a = "a",```<br />
    ```var b = "b",```<br />
    ```var c = "c",```<br />
    ```var d = "d"```<br />

    ```let a = "a",```<br />
    ```let b = "b",```<br />
    ```let c = "c",```<br />
    ```let d = "d"```<br />

    ```const a = "a",```<br />
    ```const b = "b",```<br />
    ```const c = "c",```<br />
    ```const d = "d"```<br />

* Evite ficar chamando um mesmo elemento do DOM várias vezes, adicione ele em variáveis:

    *É melhor fazer isso:*<br />
    ```//Em javascript```<br />
    ```const meuId = document.getElementById('meu_id');```<br />
    ```meuId.addEventListener('click',() => { return false; });```<br />
    ```meuId.innerHTML = "texto";```<br />
    ```meuId...```<br />

    ```//Em jQuery```<br />
    ```const meuId = $('#meu_id');```<br />
    ```meuId.on('click',function(){ return false; });```<br />
    ```meuId.html('texto');```<br />
    ```meuId...```<br />

* Evite a manipulação do DOM dentro de um loop, claro as vezes será preciso, mas evite essa ocasião que muitos fazem:

    ```let meuArray = ['texto1','texto2','texto3','texto4','texto5'];```<br />
    ```let meuHtml = '';```<br />

    ```//Em javascript```<br />
    ```const meuId = document.getElementById('meu_id');```<br />
    ```meuArray.map((txt) => {```<br />
    ```    meuHtml += txt;```<br />
    ```});```<br />
    ```meuId.innerHTML = meuHtml;```<br />

    ```//Em jQuery```<br />
    ```const meuId = $('#meu_id');```<br />
    ```$.each(meuArray,function(i,txt){```<br />
    ```    meuHtml += txt;```<br />
    ```});```<br />
    ```meuId.html(meuHtml);```<br />


    *A maneira errada seria essa:*

    ```//Em javascript```<br />
    ```meuArray.map((txt) => {```<br />
    ```    document.getElementById('meu_id').innerHTML += txt;```<br />
    ```});```<br />

    ```//Em jQuery```<br />
    ```$.each(meuArray,function(i,txt){```<br />
    ```    $('#meu_id').append(txt);```<br />
    ```});```<br />

* Sempre comente os parâmetros de suas functions e quando for utilizar mais de dois parâmetros, utilize-as como um objeto:

    *Faça assim:*<br />
    ```/*```<br />
    ```    @param1: String,```<br />
    ```    @param2: {```<br />
    ```        name: String,```<br />
    ```        idade: Number,```<br />
    ```        list: Array```<br />
    ```    }```<br />
    ```*/```<br />
    ```function minhaFuncao(param1,param2){```<br />
    ```    // param1 é uma String :)```<br />
    ```    // param2 é um Objeto :)```<br />
    ```}```<br />
    Por enquanto é só :).