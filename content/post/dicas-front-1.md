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
```html
<!-- para id utilize sempre underscore e evite utilizar letras maiúsculas -->
<div id="meu_super_id"></div>

<!-- para class utilize sempre dash e tente criar até três nomes entre os traços -->
<div class="minha-super-class"></div>
```
* Siga sempre a mesma ordem quando adicionar os atributos em suas tags:
```html
<!--
    Siga sempre essa ordem e logo após adicione os outros atributos dependendo da tag utilizada
    como por exemplo um input:
    <input id="" class="" data-input="" name="" placeholder="" value="">
    o importante é seguir sempre um padrão
-->

<!-- É mais fácil vizualizar isso: -->
<div id="primeiro_id" class="segundo-class" data-atributo="terceiro-data-atributte">
<div id="primeiro_id" class="segundo-class" data-atributo="terceiro-data-atributte">
<div id="primeiro_id" class="segundo-class" data-atributo="terceiro-data-atributte">


<!-- Do que visualizar isso: -->
<div id="primeiro_id" class="segundo-class" data-atributo="terceiro-data-atributte">
<div id="primeiro_id" data-atributo="terceiro-data-atributte" class="segundo-class">
<div data-atributo="terceiro-data-atributte" id="primeiro_id" class="segundo-class">
```
Sempre siga padrões, se você decide começar de um jeito, termine ele do mesmo jeito que você o começou.
* Chame sempre seu arquivo .css no topo da página logo após a tag <title>
* Chame sempre seu arquivo .js no fim da página dantes do fechamento da tag <\/body>

### Css
O famoso [Cascading Style Sheet](https://pt.wikipedia.org/wiki/Cascading_Style_Sheets), é também muito complicado de deixar bem estruturado.
* Como abordei acima - mantenha padrões.
* Tente seguir a estrutura do css de acordo com a estrutura do html - siga por heranças e de cima para baixo:
```css
/* Por exemplo é bem melhor utilizar isso: */

body{}

.header{}
.header .menu{}

.section{}
.section .text{}

.footer{}
.footer .copyright{}

/* Do que utilizar isso: */

.header{}
.footer .copyright{}
body{}
.footer{}
.section .text{}
.header .menu{}
.section{}

```
Pequenos detalhes fazem muita diferença.
* Tente utilizar até o máximo de três itens para definir estilo a um elemento:
```css
/* Faça isso */

.header .navigation .menu{}
.menu .menu-li{}
.menu .menu-li .menu-a{}

/* Ou apenas isso: */

.menu{}
.menu-li{}
.menu-a{}


/* Evite fazer isso: */
html body .container .header .navigation .menu{}
html body .container .header .navigation .menu .menu-li{}
html body .container .header .navigation .menu .menu-li .menu-a{}
/* Sério, evite isso, ou qualquer coisa parecida */
```
* Quando aplicar estilo a mais de um seletor sempre de uma quebra de linha
```css
/* Faça assim: */
.item-1,
.item-2,
.item-3,
.item-4{
    display:block;
    width:100%;
}

/* Evite isso, dependendo das classes utilizadas, se torna uma grande bagunça: */
.item-1,.item-2,.item-3,.item-4{
    display:block;
    width:100%;
}
```
* Quando existe apenas um estilo aplicado, deixe o mesmo sem quebra de linha:
```css
.item{ display:block; }
```
* Evite ficar utilizando o !important, na maioria das vezes quando utilizamos isso é porque estruturamos o css de maneira errada.
### Javascript | jQuery
Utilizado para criar mágica em nossas páginas, aqui está o [Javascript](https://pt.wikipedia.org/wiki/JavaScript) e sua lib mais conhecida [jQuery](https://jquery.com/).
* Siga sempre um padrão de camelcase sempre quando precisar utilizar mais de um nome para determinada, variavel, funcão, classe ou o que for.
* Tente ao máximo não repetir o código.
* Declarar váriáveis (var,let,const) - apenas uma vez:
```javascript
//É mais performático utilizar assim:
var a = "a",
    b = "b",
    c = "c",
    d = "d";

let a = "a",
    b = "b",
    c = "c",
    d = "d";

const a = "a",
    b = "b",
    c = "c",
    d = "d";

// Ou até mesmo assim:
var a = "a", b = "b", c = "c", d = "d";
let a = "a", b = "b", c = "c", d = "d";
const a = "a", b = "b", c = "c", d = "d";


// É melhor do que fazer isso:

var a = "a",
var b = "b",
var c = "c",
var d = "d"

let a = "a",
let b = "b",
let c = "c",
let d = "d"

const a = "a",
const b = "b",
const c = "c",
const d = "d"
```
* Evite ficar chamando um mesmo elemento do DOM várias vezes, adicione ele em variáveis:
```javascript
//É melhor fazer isso:

//Em javascript
const meuId = document.getElementById('meu_id');
meuId.addEventListener('click',() => { return false; });
meuId.innerHTML = "texto";
meuId...

//Em jQuery
const meuId = $('#meu_id');
meuId.on('click',function(){ return false; });
meuId.html('texto');
meuId...

```
* Evite a manipulação do DOM dentro de um loop, claro as vezes será preciso, mas evite essa ocasião que muitos fazem:
```javascript

let meuArray = ['texto1','texto2','texto3','texto4','texto5'];
let meuHtml = '';

//Em javascript
const meuId = document.getElementById('meu_id');
meuArray.map((txt) => {
    meuHtml += txt;
});
meuId.innerHTML = meuHtml;

//Em jQuery
const meuId = $('#meu_id');
$.each(meuArray,function(i,txt){
    meuHtml += txt;
});
meuId.html(meuHtml);


// A maneira errada seria essa:

//Em javascript
meuArray.map((txt) => {
    document.getElementById('meu_id').innerHTML += txt;
});

//Em jQuery
$.each(meuArray,function(i,txt){
    $('#meu_id').append(txt);
});

```
* Sempre comente os parâmetros de suas functions e quando for utilizar mais de dois parâmetros, utilize-as como um objeto:
```javascript

// Faça assim:
/*
    @param1: String,
    @param2: {
        name: String,
        idade: Number,
        list: Array
    }
*/
function minhaFuncao(param1,param2){
    // param1 é uma String :)
    // param2 é um Objeto :)
}

```
Por enquanto é só :).