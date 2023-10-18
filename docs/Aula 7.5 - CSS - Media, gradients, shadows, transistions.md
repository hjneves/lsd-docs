MEDIA em HTML5, Shadows
-----------------------

### AUDIO

* Site musicas e sfx demo: Bensound
* se remover altura da div no id `#imageHeading` ele ajusta altura à imagem
* Usar max-height no container para que a conteúdo diminua quando se torna muito pequena

```html
<audio controls loop muted preload>
  <source src="audio/4estacoes.ogg" type="audio/ogg">
  <source src="audio/4estacoes.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

### VIDEO

* como fundo usar de forma a tipografia ser legível
* sem som (ver autoplay)
* AUTOPLAY só funciona bem no refesh com muted=true - protecção dos browers para páginas ruidosas
* The video should display a placeholder image,
* **Bandwidth is a big deal**. The video needs to be small, and compressed as effectively as possible.Try to keep the video under 5mb; ideally, under 500k.
* <https://videos.pexels.com>

```css
.video {
  position: fixed;
  min-height: 100%;
  min-width: 100%;
  top:0;
  left:0;
  z-index: -1;
}

```

```html

<video class="video" autoplay muted=true loop poster="images/pordosol.png" >
  <source src="videos/pordosol.mp4" type="video/mp4">
</video>
```

FONT AWESOME
============

* W3Schools <http://www.w3schools.com/icons/>
* Usar icons com base em fontes (escalávels, vector, retina)
* usar com `<i>` ou` <span>`

```css
<link rel="stylesheet" href="http://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.4.0/css/font-awesome.min.css">


<i class="fa fa-quote-left"></i>

```

BUTTONS vs. LINKS
-----------------

BUTTONS

* implica uma acção que altera conteúdos no site, compras, registos, pesquisas

LINKS

* mais relacionado com navegação

### Tipos de botões 

button - The button is a clickable button
submit - The button is a submit button (submits form-data)
reset - The button is a reset button (resets the form-data to its initial values)

```html
 <button type="button" class="btnBuy">COMPRAR</div>
```

BACKGROUND DIV
--------------

### IMAGEM

```css
background-image: url('images/search.png');
background-repeat: no-repeat; /* */
background-position: right center;
background-size: auto 100%; /* width auto e height a 100% */
```

### **GRADIENTES**


```css
background: #8C4742; /* For browsers that do not support gradients */
background: -webkit-linear-gradient(#8C4742, #CC4762, #8C4742); /* For Safari 5.1 to 6.0 */
background: -o-linear-gradient(#8C4742, #CC4762, #8C4742); /* For Opera 11.1 to 12.0 */
background: -moz-linear-gradient(#8C4742, #CC4762, #8C4742); /* For Firefox 3.6 to 15 */
background: linear-gradient(#8C4742, #CC4762, #8C4742); /* Standard syntax */

```

### **SHADOWS**

```css
box-shadow: none|h-offset v-offset blur spread color |inset|initial|inherit;


/* offset x e y a 0, blur de 63px, spread 0 e color, com transparencia   */
box-shadow: 0 0 63px 0 rgba(113, 83, 83, 0.25);
```

Exemplo com button

```html
<button>Welcome</button>
```


```css
.welcome button {
	width: 120px;
	height: 40px;
	border-width: 0;
	border-radius: 20px;
	background: linear-gradient( to top right, #ffffff, rgb(197, 194, 194));
	box-shadow: 0px 0px 16px #9d8ba0b7;

}
```

### **TRANSITIONS**

A simple way to animate a CSS propery from an **initial** state to an end **state**


```html
<button class="btn">
  Hello World
</button>
```


```css
.welcome button {
	width: 120px;
	height: 40px;
	border-width: 0;
	border-radius: 20px;
	background: linear-gradient( to top right, #ffffff, rgb(197, 194, 194)) ;
	box-shadow: 0px 0px 16px #9d8ba0b7;
	transition: transform 250ms, opacity 250ms;
}

.welcome button:hover {
	transform: translateY(-10px);
	opacity: 0.6;
}
```

