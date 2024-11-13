
## O que é?

A aplicação de estilos ao html é o que permite formatar cada elemento de forma a atingir o layout pretendido. Os estilos são definidos através de propriedades CSS

CSS - Cascade Style sheet

As regras CSS estão associadas aos elementos que aparecem na página html. e têm o seguinte formato:

![[Pasted image 20231020142955.png]]

## inline css

Usar css directamente nas tags html não é o mais correcto:

- código difícil de interpretar e mal organizado
- aplicar uma alteração (exemplo mudar uma cor) em vários `<p>` teria de ser feito um a um o que seria uma fontes de erros e de difícil manutenção.

```html
<p style="font-family: Helvetica; font-size:150%;">This domain is established to be used for illustrative examples in documents. You may use this
domain in examples without prior coordination or asking for permission.</p>
```

## internal css

Criam-se os estilos na secção `<style> `que fica dentro do `<head>` de um documento html
Ex. coloca todos os parágrafos `<p>` com o texto branco e com o fundo a azul

```html
<style type="text/css">
    p {
        background-color: blue;
        color: white;
     }
</style>
```

## external css

Neste caso as regras CSS são definidas num ficheiro separados (por ex. styles.css) sendo depois importado no documento html.

Neste exemplo, está a ser importado o ficheiro styles.css que se encontra directoria css do projeto:
```html
<head>  
   <link rel="stylesheet" href="css/styles.css">  
</head>
```

Todas as regras definidas em styles.css passam a aplicar-se ao html do documento. Uma das vantagens do css externo é poder ser reutilizado em vários documentos html. As alterações de CSS apenas são realizadas num único ficheiro css.

## Seletores simples

Numa regra CSS os selectores determina que tags html vão ser formatadas por um conjunto de regras css.

Existem 3 tipos de seletores fundamentais: html tag, class e id

### html tag

Quando um selector é uma tag html, as regras css definidas vão ser aplicadas a todas as tags html que se encontram no documento.

Neste exemplo, todos os parágrafos do documento vão ser formatados com uma determinada cor
```css
p {
     color:#808080;
}

<p> Welcome to CSS </p>
```


### Class(.)
A class é uma tag que identifica um determinado estilo. Permite ser aplicada em vários locais no documento, e uma tag html pode receber várias classes, como no exemplo seguinte:

```css
.paragrafo {
    font-family: helvetica;
    font-size: 1.2em;
}

.azul {
     color:blue
}

<p class="paragrafo azul"> Welcome to CSS </p>
```

### Id(#)
O id é basicamente igual à classe mas por convenção é esperado que se use unicamente uma vez na página. O facto de ser único na página permite mais facilmente ser encontrado através de javascript

```css
#bck-format {
    background-color: gray;
}

<nav id="bck-format"> About | Products | Services | Contacts </div>
```

Quando queremos formatar apenas um parte de um parágrafo (por ex. uma palavra) devemos usar a tag `<span>`para englobar a parte a formatar e depois atribuir-lhe a classe pretendida.

```css
.red {
  color: red;
}

<p id="destaque"> Atention: Site maintenance during <span class="red"> 12/Dec </span></p>
```

## Seletores compostos
Por vezes queremos formatar de igual forma elementos que se encontram dentro de outros elementos. Nesta situação podemos usar um seletor composto para este efeito.

Neste ex. vamos formatar todos os parágrafos de um artigo com uma determinada cor.
```css
  .info p {
      color: gray;
    }
```
```html
  <article class='info'>
    <p>Parágrafo 1</p>
    <p>Parágrafo 2</p>
    <p>Parágrafo 3</p>
</article>
```
Este seletor vai aplicar as regras css a todos os `<p>`que se encontram dentro de um elemento com a classe `info`.

Podemos também ter seletores que são tags dentro de tags ou tags dentro de id's

Outra forma de formatar elementos de forma transversal é atribuindo classes ao elementos mas formatando-os conforme o tipo de elemento.

Por ex. estamos a usar uma classe `center`, mas queremos formatar apenas os parágrafos. 
```css
p.center {
  text-align: center;
  color: red;
}
```

```html

<h1 class="center">This heading will not be affected</h1>
<p class="center">This paragraph will be red and center-aligned.</p> 
```
Ou seja, este seletor aplica as regras css a todos os parágrafos que tenham a class `center`atribuída.

## Pseudo-classes
As pseudo-classes permitem formatar um elemento quando este se encontra num determinado estado. Por exemplo, em desktop, quando o rato passa por cima de um elemento este fica no estado de `hover`. Ou um link numa página quando é visitado, fica no estado `visited`.

Por ex.
```css
/* Formata link não visitado */
  a:link {
      text-decoration: none;
      color: gray;
    }
```
```css
/* Formata link visitado */
a:visited {
      color: gray;
    }

/* Formata link quando sob o rato */
a:hover {
      color: darkgray;
    }

/* Formata link quando em button down */
a:active {
      color: lightgray;
    }
```
Neste caso todos os links da página vão ser cinza escuro, sem sublinhado enquanto não forem visitados. Após visita passarão a cinza.

Outro exemplo é o `hover`. Se quisermos por exemplo formatar um link quando o rato está por cima podemos usar esta pseudo-classe com neste exemplo:
```css
    a:hover {
      border-bottom: 2px gray solid;
    }
```
Todos os links vão apresentar um border em baixo quando o rato passar por cima deles. Só aplica as regras enquanto se verificar a situação de hover, no instante em que deixar de estar com hover esta regra é retirada.

## Pseudo-elementos
Os pseudo-elementos são "elementos" que podem ser adicionados aos elementos html e que podem ser formatados em css para obter de forma mais simples e sem adicionar mais html algumas formatações.

`::before` e `::after`

Estes dois pseudo-elementos adicionam um novo "elemento" com conteúdo (ainda que possa ser uma string vazia) imediatamente antes e depois de um elemento 

Por exemplo:
```css
a::before {
  content:">";
}

a::after {
  content:"<";
}
```
```html
<div><a href="#">Info</a></div>
```
![[Pasted image 20231023173136.png|200]]

Um caso interessante poderá ser a utilização destes pseudo-elementos para formatar um link indicando que é um link externo

Por ex.
```css
a::after {
    background-image: url(https://s3-us-west-2.amazonaws.com/s.cdpn.io/161359/open-in-new.svg);
    background-size: contain;
    content:"";
    display: inline-block;
    vertical-align: middle;
    width: 1em;
    height: 1em;
}
```
![[Pasted image 20231023173701.png|200]]

O content é obrigatório que exista, ainda que vazio, as restantes propriedades são aplicadas como se de um elemento normal se tratasse.

Ver mais https://web.dev/learn/css/pseudo-elements

## Cascading, Inheritance & Specificity

Quando temos regras aplicadas em várias classes, id's e tags qual a ordem em que são aplicadas, existem prioridades? Os conceitos seguintes determinam como as regas CSS são aplicadas aos elementos

### Cascading [](https://web.dev/learn/css/the-cascade)

Um conjunto de regras CSS é aplicado começando pelas regras de cima até às regras em baixo. Ou seja, a ordem pela qual são escritas importa e quando duas regras (com a mesma especificidade) se aplicam a um elemento, a que está em último no documento é que prevalece

```css

.text-color {
  color: gray;
}

.destaque {
    font-size: 1.2em;
    color: black;
}

<p class="destaque text-color">Hello World</p>
```

O texto no parágrafo ficará a preto.

### Inheritance [](https://web.dev/learn/css/inheritance)

Algumas propriedades CSS definidas num elemento pai são herdadas pelos seus filhos, mas a maioria não. Isto pode parecer confuso mas é a base para se escrever menos ciências

Propriedades como `color`  e `font-family` são herdadas e por isso é que elas são normalmente definidas no body. 

```css

html {
  color: #141414;
}

body {
  font-size: 1.2em;
}


<article>
  <p>Lorem ipsum dolor sit amet.</p>
</article>

```

Neste caso tanto o `article` como o parágrafo `p` vão assumir o `font-size` definido no `body`
### Specificity [](https://web.dev/learn/css/specificity)

À medida que a diversas regras CSS vão sendo aplicadas a um elemento, algumas podem entrar em conflito, sendo necessário ordená-las e aplicá-las segundo a sua especificidade. Cada seletor tem uma pontuação de especificidade, sendo esta a ordem dos mais para os menos pontuados

1. id's
2. classes e Pseudo classes
3. elementos 
4. seletor universal (\*)

Quando há conflito de regras num elemento html, ganha a que tiver maior pontuação/especificidade. 

A keyword `!important`atribui a uma regra a maior especificidade, sendo esta a aplicada ao elemento

## Algumas propriedades

### Fontes

Na declaração da fonte usando a propriedade `font-family` pode ser especificado fontes alternativas (fallback fonts), separadas por vírgulas. Começa por tentar usar a fonte mais à esquerda, caso não consiga, avança pela direita até à fonte genérica

```css
body {
    font-family: "Times New Roman", Georgia, Serif;
    font-size: 1.2em;
}
```

```css
font-weight: bold
font-style: italic
text-decoration: underline
```


### Fontes remotas

Fontes remotas são disponibilizadas por serviços como por exemplo o [Google Fonts](https://fonts.google.com)
Podemos adicionar os estilos que queremos de uma ou mais fontes a uma coleção ficando o acessível o código dos links para incluir no documento e a font-family a usar

Ex. link's para as fontes remotas criadas no Google Fonts, neste caso a fonte Roboto Flex com alguns estilos (font-weight)

```css
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto+Flex:opsz,wght@8..144,200;8..144,300;8..144,400;8..144,500;8..144,600&display=swap" rel="stylesheet">

<style>
	body {
     	font-family: 'Roboto Flex', sans-serif;
	}
</style>
```

### Fontes locais

Existem um conjunto de fontes designadas de *[web-safe](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals#web_safe_fonts)* que existem em todos os browsers mais atuais e que  podem ser utilizadas sem necessidade de importar fontes externas. 
É uma lista limitada e por esse motivo existe a possibilidade de criar as nossas próprias famílias de fontes para poder usar numa página, através das regras `@font-face`.

Numa regra `@font-face` define-se o nome que queremos para a fonte (`font-family`) e qual o local onde se encontra o ficheiro da fonte (`src`). 

No ex. seguinte estamos criar duas fontes. Uma com o nome RobotoLight e a outra RobotoRegular, cada uma delas aponta para um ficheiro com uma variação de estilo da fonte:

```css
@font-face {
  font-family: RobotoLight;
  src: url('fonts/Roboto/Roboto-Light.ttf') ;
}

@font-face {
  font-family: RobotoRegular;
  src: url('fonts/Roboto/Roboto-Regular.ttf') ;
}

```


#### Tamanho da fonte

 O tamanho da fonte pode ser definido de diversas formas:

- px - pixéis, valor fixo
- pt - pontos, valor fixo
- % - percentagem relativamente ao elemento pai ( default no browser para o body)
- em - "em's" tamanho escalável mais adequado para mobile, `1 em` corresponde ao font-size definido no elemento container
- rem - semelhante ao "em", mas o tamanho é sempre relativo ao tamanho base (root, normalmente 16px) 

Relação de dimensão entre os diversos formatos
1em ~ 100% ~ 12pt ~16px

Alguns exemplos:
`font-size: 120%` (em % e relativo ao tamanho do elemento parent)
`font-size: 20px` 
`font-size: 1.2em 

Artigo sobre a utilização destes formatos
<http://kyleschaeffer.com/development/css-font-size-em-vs-px-vs-pt-vs/>

Uma boa prática será usar uma base percentual no `<body>` e depois **em** ou **%** nos elementos



### Cores

A propriedade `color` permite formatar a cor do texto. As cores podem ser definidas por nome, código hexadecimal ou RGB.

https://htmlcolorcodes.com

Ex. define a cor do texto no body a branco.
```css
body {
  color: #ffffff
}
```

Neste exemplo estamos a formatar a cor de fundo a branco mas com uma transparência de 50%, para isso usámos a função `rgba`.
Tipicamente é uma solução utilizada para criar fundos com transparência em `div`'s que têm conteúdo:
```css
.box {
	background-color: rgba(0, 0, 0, 0.5);
	color: white;
 }
```

![[Pasted image 20231020175851.png]]

### Box model

Este modelo que podemos encontrar nas *developer tools* dos browsers ilustram como os elementos html de uma página são estruturados, ao nível da sua dimensão e espaçamento.
Cada elemento tem:
- dimensão intrínseca (azul) - dimensão especificada pelo `width`e `height`no css
- padding (verde) - espaçamento entre o limite do elemento e o seu conteúdo
- border (amarelo) - dimensão da borda do elemento
- margin (laranja) - espaçamento entre o limite do elemento face ao elementos irmão ou pai

![[Pasted image 20231020180652.png|400]]

A dimensão real do elemento no UI engloba a sua dimensão intrínseca (794x160) o padding e a border.
Neste exemplo temos uma elemento que vai ocupar 864x260 (o padding e a border contam duas vezes em largura e altura)

>[!tip] Nota
>Por vezes não queremos que o padding e a border alterem a dimensão especificada para os elementos. Neste caso existe uma propriedade `box-sizing: border-box;`que permite ao elemento incluir tanto o padding como a border no seu tamanho.

### Object-fit

Nos elementos imagem e video com esta propriedade é possíovel controlar a aparencia da imagem em relação à dimensão definida do container com `width`e `height`.  Por exemplo uma imagem retangular onde queremos apresentar num quadrado, vai ter de sofrer um clipping, caso contrário ficará distorcida. Neste caso seria necessário aplicar a propriedade `object-fit: cover`. Outra hipótese seria apresentá-la como fundo de um elemento `div`.

Exemplo:
```css
section img {
  width: 180px;
  height: 180px;
  border: 5px solid white;
  border-radius: 50%;
  object-fit: cover;
}
```

### Borders

As borders são o contorno do elemento e podem ser especificadas através da propriedade `border`.

Existe propriedade desdobra-se em várias outras propriedade para se formatar o cor, a espessura, o estilo e a curvatura nos cantos.
Alguns exemplos:
```css
border-style: solid;
border-width: 2px;
border-color: black;
border-radius: 2em;
```

> [!tip] Tip
>Se criarmos um elemento quadrado com 20px de dimensão e aplicarmos uma `border-radius: 50%` , ou seja, com metade da dimensão do elemento, vai  curvar os cantos num equivalente a transformar o elemento num círculo

Existe uma forma abreviada de aplicar várias destas propriedade. Neste exemplo estamos a aplica uma borda com 2px de dimensão, preta e sólida
```css
border: 2px black solid;
```

Podem o consultar mais propriedade aqui no [w3school](https://www.w3schools.com/css/css_border.asp).

### Margin & Padding

Tanto a margin como o padding pode ser definido em cada lado do elemento `left`, `top`, `rigth`e `bottom`.
Notar que se o elemento for inline (ver display) a margin apenas é aplicada ao `left`e `right`. Já no caso do padding pode ser aplicado em todas as direcções.

Por ex. 
```css
margin: 50px;
``` 
cria  uma margem de 50px a toda a volta do elemento

```css
margin-left: 100px;
``` 
altera apenas a margem da esquerda (existe tb para right, top e bottom)

```css
margin: 10px 20px 10px 20px;
``` 
Especifica as 4 margens começando na top e avançando no sentido horário dos ponteiros (right, bottom, left).

```css
margin: 10px 20px;
``` 
Especifica a margem top e bottom (10px) e a left e right (20px)

Neste exemplo usamos o `auto` como margem left e right, para centrar o elemento
```css
width: 768px;
margin: 0 auto;
```


O padding é semelhante a uma margem mas para dentro do elemento, e por defeito altera o tamanho do elemento.

```css
div {
     padding: 10px;
}
```

> [!tip] Nota
> Quando tempos parágrafos dentro de uma `div` temos de colocar as suas margens a 0 para que os 10 px fiquem correctos em todos os lados


### Width e height

As dimensões de um elemento são definidas pelo seu `width`e `height`. Estas propriedades css podem ser definidas em valor absoluto (por ex. pixéis) ou em valor relativo.

Por ex.
```css
box {
    height: 250px;
    width: 250px;
}
```

Ou por ex.
```css
box {
    height: 250px;
    width: 50%;
}
```

No caso do `width`o valor percentual é sempre relativamente ao `width` do elemento pai.
No caso do `height` o  valor percentual é calculado em função do `height`do elemento pai se este tiver uma altura calculada. Caso contrário fica em auto, ajustando a altura do seu conteudo.

Muitas vezes em landing pages queremos que ela tenha um height que ocupe todo o viewport (janela do browser) em altura.

Existem algumas formas de o fazer com por exemplo neste exemplo. O fica com position absolute (ver position) e com altura de 100%, sendo assim possível calcular a sua altura. Se tivermos uma div com `height` a 100% ela vai aceitar o valor. 
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

Outra hipótese é usar a unidade *vh - viewport height* - que é um valor percentual mas relativo ao viewport (janela do browser)

```css
  height: 100vh;
```

### Alinhamento de texto

O alinhamento do texto é normalmente usado com outras propriedades css para se obter o layout pretendido. 
```css
p {
  text-align: justify; /* existe também left, right e center */ 
}
```

### Overflow

Esta propriedade permite controlar como um elemento, com uma dimensão fixa,  trata o seu conteúdo quando este ultrapassa os seus limites.

Por exemplo se utilizarmos uma imagem ou texto dentro de uma div, mas quisermos garantir que o seu tamanho não ultrapassa as dimensões da div onde se encontra, podemos usar o valor `hidden`na propriedade overflow. 

```html
.landingImage {
		height: 200px;
		width: 200px;
		overflow: hidden;
}

<div class="landingImage">
		<img src="images/back1.jpg">
</div>
```

### Imagens de fundo 

Uma div para além de poder como fundo uma cor sólida ou um gradiente, também pode ter uma imagem. Neste caso todo o conteúdo da div vai aparecer sobre a imagem de fundo.

É normalmente utilizada em headings, sliders e tem a vantagem de ser facilmente adaptável aos diversos tipos de ecrãs. A proporção da imagem pode ser controlada de forma a que a imagem não se distorça quando as dimensões da div se alteram de forma não proporcional.

Por ex.
```css
.imageHeading {
	height: 400px;
	background-image: url("../images/img1.jpg");
	background-size: cover;
	background-position: center center;
}
```
Neste caso a imagem vai ter um tamanho de `cover`, o que significa que a imagem vai ser ajustada no tamanho para ocupar sempre toda a div e em termos de posição vai estar centrada tanto na horizontal (eixo x) como na vertical (eixo y). 

### Gradientes

Existem vários tipos de gradientes, lineares, radiais e cónicos. Um gradiente linear pode ser criados com a função `linear-gradient`atribuída à propriedade `background`. Os gradientes podem ser criados usando pelo menos duas cores e uma direção.

Neste exemplo, temos um gradiente linear que vai transitar da cor `#3c0000`para a cor `#9948d9`partindo do canto inferior esquerdo para o canto superior direito.
```css

.intro {
	background: #8C4742; /* fallboack color for browsers that do not support gradients */
	  width: 100%;
	  background: linear-gradient(to top right, #3c0000, #9948d9);
	  padding: 7rem 2rem 4rem 2rem;
}
```

Mais sobre [gradientes](https://web.dev/learn/css/gradients)

### Sombras

Através da propriedade `box-shadow`podemos criar uma sombra por debaixo do elemento div. Esta sombra pode ser manipulada em termos de offset, blur, spread e côr. Existe também a propriedade `text-shadow` utilizada para texto e a propriedade `drop-shadow` que pode ser aplicada a uma imagem com transparência.

Neste exemplo temos um botão com uma sombra esbatida em toda a sua volta:
```css
 .audio button {
   color: white;
   width: 200px;
   height: 40px;
   font-size: 1.2rem;
   border-radius: 20px;
   border: none;
   /* offset x e y a 0, blur de 24px e de côr preta   */
   box-shadow: 0px 0px 24px black;
}
```
```html
<div class="audio">
  <button>Enter</button>
</div>
```
![[Pasted image 20231024103506.png|300]]

As propriedade mais utilizadas são:
**offset x e y** - defasamento de posição do fundo relativamente à posição do elemento. Relativo ao canto superior esquerdo
**blur** - quantidade de esbatimento para a sombra
**spread radius (opcional)** - quantidade de sombra que se espalha para além da borda do elemento.

Mais sobre [sombras](https://web.dev/learn/css/shadows).

### Display

Este propriedade define como o elemento é apresentado numa página. Todos os elementos têm um display por default. Por ex. os links `<a>`, as imagens `<img>` ou os `<span>`são elementos com display **inline**. Já por ex. as `<div>` e os parágrafos `<p>` são elementos com display **block**

Os tipos de display mais comuns são:

**`block`**:  bloco retangular na página que ocupa, por defeito, toda a largura do elemento pai e começam sempre numa nova linha. As suas dimensões são configuráveis.

**`inline`**: os elementos são colocadas uns a seguir aos outros na mesma linha, se possível. Existem uma variação, a `inline-block` que permite colocar os elementos em linha mas garante as propriedade do `block`. Este display é muito usado quando queremos configurar uma menu horizontal com recurso a `<li>`.

>[!tip] Espaço entre elementos inline
>Os browsers adicionam um espaço entre os elementos com display `inline`, à semelhança dos espaço entre palavras. Este espaço uma grande parte das vezes não se pretende, pelo que existem alguns workarounds para os eliminar. Uma das formas é a apresentada no snippet a seguir, colocando o inicio de um elemento imediatamente a seguir ao fecho do anterior. ([ver mais](https://css-tricks.com/fighting-the-space-between-inline-block-elements/))

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

**`none`**: Esconde o elemento

**`flex`**: Define um elemento como um flex container. Este elemento passa ter um comportamento que está ligado directamente ao seus elementos filho diretos. (ver secção Flexbox)

### Float

A propriedade css `float` especifica que o elemento html deve ser retirado do fluxo normal de rendering para ser colocado à esquerda ou direita dentro do seu elemento pai. Não existe float ao centro. Se existirem elementos com display inline este vão rodeá-lo conforme os espaço disponível.


CSS property specifies that an element should be taken from the normal flow and placed along the left or right side of its container, where text and inline elements will wrap around it.

Neste exemplo, temos duas caixas, uma vai flutuar à esquerda e a outra vai flutuar à direita. Como as suas larguras não ultrapassam 100% do elemento pai, elas vão ficar lado a lado.
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

<div>
	<div class="floatLeft"><p> Float left DIV </p></div>
	<div class="floatRight"><p> Float right DIV </p></div>
</div>
```

Se colocarmos vários elemento a flutuar à esquerda, eles vão-se alinhando sucessivamente à direita do anterior, enquanto existir espaço disponível em largura.

Neste exemplo os 3 cartões vão estar todos na mesma linha e alinhados À esquerda
```html
.card {
  float: left;
  width: 25%;
  height: 50px;
}

<div>
	<p class="card"> Contacto1</p>
	<p class="card"> Contacto2</p>
	<p class="card"> Contacto3</p>
</div>
```

Depois de uma secção com elementos float, normalmente queremos que o conteúdo seguinte comece numa linha nova, o que pode não acontecer se existir algum espaço deixado pelos elementos float.
Existe a possibilidade de efectuar um clear do float antes do conteúdo novo, para que este comece sempre numa linha nova.

```css
.card {
  float: left;
  width: 25%;
  height: 50px;
}

.clear {
    clear: both;
}

<div>
	<p class="card"> Contacto1</p>
	<p class="card"> Contacto2</p>
	<p class="card"> Contacto3</p>
</div>
<div class="clear"></div>
```

### Flexbox

A flexbox é um modelo de layout CSS que é muito usada para estruturar uma página html, sendo a base de muitas frameworks css. Tem por base um elemento play com `display: flex;` e uma série de elementos filhos diretos que se organizam mediante a configuração da flexbox.

Por defeito os elementos numa flexbox são colocados lado a lado e ocupam os espaço necessário para o seu conteúdo.

No exemplo seguinte temos uma grid de 3 elementos colocados lado a lado, onde cada elemento tem o seu próprio tamanho.
```css
.box {
	display: flex;
	flex-direction: row; /* valor por defeito */
	gap: 5px; /* espaço a colocar entre os elementos da flexbox*/
}

.box div {
	background-color: chocolate;
	height: 140px;
	padding: 6px;
	box-sizing: border-box;
}
```

```html
<div class="box">
	<div>Info</div>
	<div>News from today</div>
	<div>Feed</div>
</div>
```

Por defeito os elementos ficam alinhados à esquerda. Podemos alterar a disposição dos elementos usando a propriedade `justify-content`.

Por ex. se quisermos os elementos centrados, esta seria a classe `box` :
```css
.grid {
	display: flex;
	flex-direction: row; /* valor por defeito */
	gap: 5px; /* espaço a colocar entre os elementos da flexbox*/
	justify-content: center;
}
```

Se quisermos que os elementos expandam até ocuparem toda a dimensão em largura da flexbox, então devemos utilizar a propriedade `flex` em cada um dos seus elementos:

Por exemplo, colocando `flex: 1` vai fazer com que os elementos se expandam de igual forma até atingirem a largura total da flexbox.
```css
.grid div {
	flex: 1;   /* expande os elementos de forma igual */
	background-color: chocolate;
	height: 140px;
	padding: 6px;
	box-sizing: border-box;
}
```

Na verdade a propriedade `flex` é um atalho para a um subconjunto de outras propriedades.
```css
flex: 0 1 auto /* shortcut for setting flex-grow, flex-shrink, flex-basis */
```

Ver guia completo da [flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) e este guia [interativo](https://www.joshwcomeau.com/css/interactive-guide-to-flexbox/) do Josh Comeau.

### Position

Enquanto o `display` define a forma com o objecto é apresentado a propriedade `position` define o tipo de posicionamento do elemento no fluxo normal do documento.
O fluxo normal do documento efetua o rendering dos elementos nos seguintes termos:

- os elementos com display block usam toda a largura do elemento que o contém, mas a sua altura depende do seu conteúdo
- os elementos block ficam uns por debaixo dos outros, na vertical, de cima para baixo.
- os elementos inline têm a dimensão do seu conteúdo,
- todos os elementos não se sobrepoem e as suas margens colapsam

Existem os seguintes tipos de position:

#### `static`

position default de todos os objectos, acompanha o fluxo normal do documento. Neste tipo de position os elementos não são afetados pelas propriedades `top`, `bottom`, `left`, e `right`.

```css
.box div {
  border: 2px solid gray;
  padding: 15px;
  margin: 15px;
}
```
```html
<div class='box'>
	<div>Info</div>
	<div>News</div>
	<div>Feed</div>
</div>
```

![[Pasted image 20231022182411.png|500]]

#### `fixed`

Um elemento com este posicionamento vai ser posicionado relativamente ao viewport, ou seja, vai estar sempre na mesma posição mesmo que existe scroll na página. As propriedades top, right, bottom e left são usadas para posicionar o elemento.

Normalmente é usado no posicionamento de menus de navegação que são fixos, ou em popup modals que ficam no centro do viewport.

Os elementos fixed saem fora do fluxo normal do documento, ou seja, não têm nenhum elemento pai que o contém, ou outros elementos não têm noção da existência deste elementos. Isto pode originar a necessidade de colocação de margens extra (por ex. num menu de navegação fixo).

```css
.box div {
  border: 2px solid gray;
  padding: 15px;
  margin: 15px;
}

nav {
  position: fixed;
  background: gray;
  padding: 15px;
  top:0;
  left:0;
  width: 100%
}
```
```html
<nav>nav</nav>

<div class='box'>
	<div>Info</div>
	<div>News</div>
	<div>Feed</div>
</div>
```

![[Pasted image 20231022184026.png|500]]

#### `relative` e  `absolute`

O posicionamento `relative` e `absolute` andam normalmente de mãos juntas. O posicionamento `relative`tem por base o `static`mas os elementos podem ser posicionados com as propriedades `top`, `bottom`, `left`, e `right`. Já os elementos posicionados com `absolute` têm por base o posicionamento `fixed`, apenas com a diferença de serem posicionados não relativamente ao viewport , mas relativamente ao primeiro elemento container que esteja posicionado como relative, absolute ou fixed. Se a página tiver scroll, os elementos absolute avançam com o scroll.

Por exemplo:
```css
.box div {
  position: absolute;
  border: 2px solid gray;
  padding: 15px;
  margin: 15px;
  bottom: 0;
  right: 0;
}

.box {
  position: relative;
  height: 200px;
  border: 2px solid blue;
}
```
```html
<div class='box'>
	<div>Info</div>
</div>
```

![[Pasted image 20231022190109.png|500]]

Os cards são normalmente criados com recurso a um container com position `relative`e com os elementos que o constituem com posicionamentos diversos, sendo que o `absolute`  será muito útil em posicionamentos forma do fluxo normal, mas apenas dentro do card container.

No entanto se um elemento posicionado `absolute` não encontrar nenhum elemento pai com posicionamento (relative, absolute, fixed) ele vai-se posicionar relativamente ao `body`do documento.

#### `sticky`

Um elemento posicionado como `sticky` fica posicionado de forma `relative`ou `fixed` conforme a posição do scroll. Assume o posicionamento `relative`até um determinado offset for alcançado no viewport. A partir daí fica fixo, assumindo um posicionamento `fixed`.

Neste exemplo temos uma caixa que vai deslizar com o scroll da página, mas ficará fixa quando chegar ao topo do viewport,
```css
 .box {
   position: sticky;
   top: 0px;
}
```

Não é suportado em  IE/Edge 15 ou anterior.

CSS Tricks
https://css-tricks.com/almanac/properties/p/position/

