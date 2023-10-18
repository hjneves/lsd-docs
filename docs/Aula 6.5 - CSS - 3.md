Vamos usar o water.css
----------------------

### water.css

https://watercss.kognise.dev/#installation

```css 
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/water.css@2/out/water.css">
```

### IMAGEM EM HEADING

usar background-image em imagens de slides ou de headings

```css
.imageHeading {
height: 400px;
background-image: url("../images/pixar-regras.jpg");
background-size: cover;
background-position: center center;
}
```

### GRID

* vamos usar `display: flex;`

```css
.grid {
	display: flex;
	flex-flow: row;
	gap: 1px;
}

.grid div {
	flex-basis: 1;
	background-color: chocolate;
	height: 140px;
	padding: 6px;
	box-sizing: border-box;
}
```

```html
<div class="grid">
	<div>Info</div>
	<div>News</div>
	<div>Feed</div>
</div>
```

#### FLEX-GROW, FLEX-SHRINK e FLEX-BASIS

https://css-tricks.com/understanding-flex-grow-flex-shrink-and-flex-basis/

```css
flex: 0 1 auto /* shorcut fror setting flex-grow, flex-shrink. flex-basis*/
```




* Separação a branco no topo da grid

- criar um `margin-top`, ou `border-top`

```css
margin-top: 1px;
```

### HOVER

```css
.grid div:hover {
	opacity: 0.5;
}
```

* Padding no conteúdo da célula grid

```css
.grid div {
  padding: 5px;
}
```

Alinhar mensagem vertical
-------------------------

* usar flexbox

```css
.headingMessage 
	height: 180px;
	display: flex;
	justify-content: space-around;
	align-items: center;
}

```

FOOTER
------

* Criar div com fundo para informação de contactos, redes sociais, etc

**CSS EXTERNOS**
----------------

Colocar no head. Por convenção o ficheiro default tem o nome de styles.css

```css
 <link rel="stylesheet" type="text/css" href="css/styles.css" />
```

External CSS

- simplificação do ficheiro html

- re-utilização em diversos ficheiros

- permite o uso de cache 

- styles.css por convenção

Outros layouts
--------------

* Layout com dimensão fixa e largura fixa
* Menu esquerda (25%), conteudo à direita (75%) e footer (100%)
