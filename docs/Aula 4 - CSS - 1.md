CSS is about styling you content built with html

Article principais príncípios.

<https://www.taniarascia.com/overview-of-css-concepts/>

CSS - Cascade Style sheet

São regras associadas aos elementos que aparecem na página html

![](DE8161473BFB8E4E4930FDA79373BBB9.jpg)

**INLINE CSS**
--------------

Usar css directamente nas tags Html.

Não é o mais correcto

- código difícil de interpretar e mal organizado

- aplicar uma alteração (exemplo mudar uma cor) em vários \<p\> teria de ser feito um a um - fontes de erros, difícil manutenção

```html
<p style="font-family: Helvetica; font-size:150%;">This domain is established to be used for illustrative examples in documents. You may use this
domain in examples without prior coordination or asking for permission.</p>
```

**INTERNAL CSS**
----------------

**
**

Criam-se styles na secção `<style> `que fica dentro do `<head>`

Ex. coloca todos os parágrafos `<p>` a azul

```html
<style type="text/css">
    p {
        font-family: Helvetica; 
        font-size:150%;
        background-color: blue;
        color: white;
     }
</style>
```

TEXT SIZE:
----------

**px** - valor fixo

**pt **- valor fixo

**%** - percentagem relativamente ao default no browser para o body

**em **- tamanho escalável mais adequado para mobile, 1 em corresponde ao font-size do documento (body)

<http://kyleschaeffer.com/development/css-font-size-em-vs-px-vs-pt-vs/>

1em ~ 100% ~ 12pt ~16px

**Boa prática:**

Usar uma base percentual BODY e depois `em` ou % nos elementos

**COLORS**
----------

you can use HTML color codes to fill color properties

```css
.color_primary {
  color: #ffffff
}
```

**DIV**

Criar div e mostrar como também ela se pode formatar

```html
<style type="text/css">
    div {
        font-family: Helvetica; 
        font-size:150%;
        background-color: blue;
        color: white;
     }
</style>
```

E também como usar a mesma formatação para 2 componentes

```html
<style type="text/css">
    div, p {
        font-family: Helvetica; 
        font-size:150%;
        background-color: blue;
        color: white;
     }
</style>
```

**BORDERS**
-----------

`border: 2px black solid `(ver diversos tipos no w3school, mas normalmente usa-se o solid e dashed

ou então

```css
border-style: solid
border-width: 2px;
border-color: black
```

`border-radius: 10px` permite curvar os cantos com um determinado raio. faz um circulo se radius igual a metade do quadrado

**MARGINS**
-----------
Margins only work horizontally—`left` and `right`—on inline-level elements. Padding works on all four sides of inline-level elements; however, the vertical `padding`—the `top` and `bottom`—may bleed into the lines above and below an element.

`margin: 50px` create an outside margin all around the DIV

`margin: top right bottom left` (no sentido dos ponteiros a partir do top) altera cada uma das margens especificamente

`margin-left: 100px` altera apenas a margen da esquerda (existe tb para right, top e bottom)

Usar a margem para centrar container:

```css
width: 768px;
margin: 0 auto;
 
```

**PADDING**
-----------

semelhante a uma margem mas para dentro do DIV.

```css

div {
     padding: 10px;
}
```

NOTA: quando tempos parágrafos dentro do DIV temos de colocar as suas margens a 0 para que os 10 px fiquem correctos em todos os lados

NOTA2: Altera o width e o height

**WIDTH e HEIGHT em %**
-----------------------

 inline-level elements will not accept the `width` and `height` properties or any values tied to them
 
WIDTH - O valor percentual % é sempre relativamente ao width do elemento pai

HEIGHT - O valor percentual é sempre em função do conteúdo do elemento pai (que por default é auto)

Muitas vezes queremos um height que ocupe o viewport (ecrã em altura )

Para isso temos de:

### 1ª Hipótese

### a) definir o elemento com height:100%

### b) definir position absolute e calcular a dimensão de height (e width) do elemento pai;

```css
body {
    font-size: 120%;
    font-family: Helvetica;
    color: gray;
    margin: 0;
    height: 100%;
    width: 100%;
    position: absolute;

}
```

### 2ª Hipótese

### a) Usar a dimensão vh;

vh - vertical heigh - Relative to 1% of the height of the viewport\*

```css
  height: 100vh;
```

### 

**ALIGNMENT**
-------------

Alinhamento do texto

###

```css
p {
  text-align: justify;
}
```

OVERFLOW
--------

Quando queremos conteúdo dentro de uma DIV mas foraçdo ao seu tamanho devemos usar a propriedade overfow nessa div

```css
overflow: hidden;
```

Por exemplo uma imagem dentro de uma DIV

```html
.landingImage {
		height: 200px;
		overflow: hidden;
		width: 200px;
}

<div class="landingImage">
		<img src="images/pixar1.jpg">
</div>

```

Classes and Id's
================

Cascading, Inheritance & Specificity
------------------------------------

The first step to gaining a stronger understanding of CSS is to learn how these three concepts together control which CSS rule applies to what element.

### Cascading

##### [](https://dev.to/frontenddude/important-css-concepts-to-learn-57j3#cascading)

Cascade is the fundamental concept on how CSS was created. As the name suggests, Stylesheets cascade (top to bottom). This means that the order of CSS rules matter and when two rules apply that have equal specificity the one that comes last in the CSS is the one that will be used.

### Inheritance

##### [](https://dev.to/frontenddude/important-css-concepts-to-learn-57j3#inheritance)

Some CSS property values set on parent elements are inherited by their child elements, and some aren't. This can often be confusing but the principle behind it is actually designed to allow us to write fewer CSS rules. 

Properties such as 'color' and 'font-family' are inherited which is why we often use the BODY element to assign them to.

It is also worth knowing that every CSS property accepts four values to control inheritance essentially being able to turn inheritance "on and off". 

### Specificity

##### [](https://dev.to/frontenddude/important-css-concepts-to-learn-57j3#specificity)

As multiple rules apply to an element conflicting rules are sorted and applied by specificity. Each selector has a different specificity ranking which are:

* **Id's**
* **Class and Pseudo Class's**
* **Element selectors**

As rules conflict, CSS determines the rule with the highest specificity and applies it to the element. 

CLASS (.) é uma tag que identifica um determinado estilo. Permite aplicar várias classes à mesma tag html, ex \<p\>

```html||css

.paragrafo {
    font-family: helvetica;
    font-size: 1.2em;
}

.azul {
     color:blue
}

<p class="paragrafo azul"> Welcome to CSS </p>
```

ID (\#) é basicamente igual à classe mas por convenção é esperado que se use unicamente uma vez na página

```html
#menu {
    background-color: gray;
}
<nav id="menu"> About | Products | Services | Contacts </div>
```

Podemos misturar várias classes

```html
.destaque {
  background-color: yellow;
}

<p class="destaque paragrafo"> Atention: Site maintenance during 12/12 </p>
```

SPAN para identificar um bocado de texto num \<p\> e formatá-lo

```html
.red {
  color: red;
}

<p id="destaque" class="paragrafo"> Atention: Site maintenance during <span class="red">12/Dec</span></p>
```

**
**

**DISPLAY**
-----------

Define como o elemento é apresentado. 

**`block`: quebra linha, aproveita todo o width do objecto**

**`inline`: apresenta um elemento a seguir a outro na mesma linha se possível (formatar `li` para menus)**

* The browser adds spaces between elements displayed `inline` and `inline-block`, just like it adds spaces between words.
* SOLUÇÔES: <https://davidwalsh.name/remove-whitespace-inline-block>
* Fim de tag e inicio da próxima na mesma linha

```
<header>...</header>
<section>
  ...
</section><section>
  ...
</section><section>
  ...
</section>
<footer>...</footer>
```

**`none`: esconde (esconde e mostra caixa de validação)**

**`flex`: defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.**

<https://css-tricks.com/snippets/css/a-guide-to-flexbox/>



**FLOAT**
---------

The `float` CSS property specifies that an element should be taken from the normal flow and placed along the left or right side of its container, where text and inline elements will wrap around it.

Usado para layout de sites e elementos que se repetem
-----------------------------------------------------

```css
 .floatLeft {
    float: left;
    background-color: lightyellow;
    width: 80%;
    height: 300px;
}

.floatRight {
    float: right;
    background-color: lightblue;
    width: 20%;
    height: 300px;
}

<div class="floatLeft"><p> Float left DIV </p></div>
<div class="floatRight"><p> Float right DIV </p></div>
```

### Usado para apresentar vários cartões

Alinha o objecto à esquerda,** um segundo objecto** com esta classe vai alinhar à direita do que está alinhado à esquerda.

Não existe **float center**!

Todo o conteúdo sem float preenche os espaços vazios por entre as DIV com float

```html
.card {
  float: left;
  width: 25%;
  height: 50px;
}

<p> Contactos</p>


```

**CLEAR FLOAT**

Normalmente queremos colocar texto logo por baixo de DIV com float.

### 1ª Opção

Colocar um div a seguir aos DIV’s com float, com uma class .clear

```css
.clear {
    clear: both;
}
```

### 2ª Opção

If an element is taller than the element containing it, and it is floated, it will overflow outside of its container.

Then we can add `overflow: auto;` to the containing element to fix this problem:

**POSITIONING**
---------------

Define o tipo de posicionamento do objectivo

### - STATIC

Base default de todos os objectos acompanha o fluxo normal do objectos

Static positioned elements are not affected by the top, bottom, left, and right properties.

### - RELATIVE

An element with position: relative; is positioned relative to its normal position.

Setting the top, right, bottom, and left properties of a relatively-positioned element will cause it to be adjusted away from its normal position. Other content will not be adjusted to fit into any gap left by the element.

Position: relative only takes top and left property 

![IMG\_2688.JPG](705D68969C307F6E0B0C75964A6F9EFB.jpg)

### - FIXED

An element with `position: fixed;` is positioned relative to the viewport, which means it always stays in the same place even if the page is scrolled. The top, right, bottom, and left properties are used to position the element.

### - ABSOLUTE

An element with position: absolute; is positioned relative to the nearest positioned ancestor (instead of positioned relative to the viewport, like fixed). Sai fora do fluxo normal de HTML, como se ficassem numa layer diferente.

However; if an absolute positioned element has no positioned ancestors, it uses the document body, and moves along with page scrolling.

### - STICKY

A sticky element toggles between `relative` and `fixed`, depending on the scroll position. It is positioned relative until a given offset position is met in the viewport - then it "sticks" in place (like position:fixed).

Note: Not supported in IE/Edge 15 or earlier. Supported in Safari from version 6.1 with a -webkit- prefix.

```css
 .box {
   position: relative 
  /* relative to its default position as static (the default when an html component is created)*/
  /* Position: relative only takes top and left property */
   z-index: 1 
  /*number to control layer position, the position property must be defined */
}
 .box {
   position: absolute 
  /* # todo o restante conteúdo ignora esta box */
}
 .box {
   position: fixed 
  /* # funciona como o absolute mas fixa o objecto na pagina, quando se faz scroll, usado em toolbars de menus */
}
 .box {
   position: sticky;
   position: -webkit-sticky;
   top: 0px;
}
 
```