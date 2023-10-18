# Animations using CSS3

CSS TRANSITIONS
-   Can only move from initial to final state — no intermediate steps
-   Can only run once
-   Require a trigger to run (like mouse hover)
-   Run forwards when triggered and in reverse when trigger is removed
-   Easier to use with JavaScript
-   Best for creating a simple change from one state to another

CSS ANIMATIONS
-   Can move from initial to final state, with intermediate steps in between
-   Can loop infinitely thanks to animation-iteration-count property
-   Can be triggered but can also run automatically
-   Can run forwards, in reverse, or alternate directions
-   More difficult to use with JavaScript
-   Best for creating a complex series of movements

## Animações Simples - CSS Transistions

Muito usado em efeitos de hover sobre elementos

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: border-radius 2s, width 2s;
  /* test with margin-left and opacity */
    }


div {
	width: 150px;
	border-radius: 8px;
}

```

The transition effect will start when the specified CSS property (width) changes value.


## Animações complexas - CSS @keyframes and animation

The main component of CSS animations is `@keyframes`, the CSS rule where animation is created. Think of `@keyframes` as being stages along a timeline. Inside `@keyframes`, you can define these stages, each having a different style declaration.

Next, to make CSS animations work, you need to bind the `@keyframes` to a selector. This will gradually parse all the code inside the `@keyframes` declarations and change the initial style to the new style, based on the stages. 

### Animação de banner info

```css
.infoBox {
	position: relative;
	overflow: hidden;
	top: 0;
	width: 100%;
	height: 30px;
	background-color: aliceblue;
}
	
.info {
	position: absolute;
	width: 100%;
	top:0;
	left: -50%;
	animation: move 16s linear infinite;
}

  @keyframes move {
	100% {
	  left: 100%;
	} 
  }
```

```html
    <div class="infoBox">
      <p class="info">Promoções de Primavera: de 26 a 29 de Março</p>
    </div>

    <div class="welcome bg-secondary text-white">
      <p class="text-center">Welcome to this site</p>
    </div>
    
```

## Uso do setTimeout e setInterval

### setTimeout

- executa uma determinada função com um atraso de x milisegundos
- Apresenta mensagem de boas vindas e depois esconde-a
- Using bootstrap to configure the banner

```html
<div class="welcome bg-secondary text-white">
      <p class="text-center">Welcome to this site</p>
</div>
```

```js
// my javascript code inside HTML
let welcome = document.querySelector('.welcome');

// calls hideMessage function after 4sec
setTimeout(hideMessage, 4000);

function hideMessage () {
  welcome.style = 'display:none';
}
```

### setInterval

- executa uma determinada função de x em x milesegundos
- Ex. apresentar as horas ou um contador
```html
<p>Clock:</p>
<p class="clock display-4">13:45:00</p>
```

```js
// Call updateTime function each second
setInterval(updateTime, 1000)

let clock = document.querySelector('.clock');

function updateTime() {
  // update clock paragraph with current hour
  clock.textContent = dayjs().format('HH:mm:ss')
}

```

## Plugin Animate.CSS

https://animate.style/

Apresentar o plugin e usar nos exercicios anteriores

1º Animar a mensagem de boas vindas com slideInDown e depois do timeout com fadeOut 

- alterar depois o tempo da animação com `animation-duration: 0.5s`

```html
 <div class="welcome bg-secondary text-white animate__animated">
      <p class="text-center">Welcome to this site</p>
</div>
    
```

```js
 function hideMessage () {
          //welcome.style = 'display:none';
          welcome.classList.add ('animate__fadeOutUp')
        }
```