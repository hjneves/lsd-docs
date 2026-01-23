Na secção de animações e transições vimos com podemos criar animações em CSS e HTML.
Como recurso ao javascript conseguimos utilizar essas animações de forma programática.

Existem duas funções em javascript que são muitas vezes usadas nalgumas pequenas animações.
## setTimeout

Executa uma determinada função com um atraso de x milisegundos.
Vamos imaginar que queremos apresentar uma mensagem ao utilizador, ma que passado algum tempo essa mensagem desapareça. Pode ser por exemplo uma mensagem de agradecimento na subscrição de uma newsletter.


```html
<div class="msg bg-secondary text-white">
      <p class="text-center">Obrigado pela subscrição</p>
</div>
```

```js
// my javascript code inside HTML
let msg = document.querySelector('.msg');

// calls hideMessage function after 4sec
setTimeout(hideMessage, 4000);

function hideMessage () {
  msg.style = 'display:none';
}
```

## setInterval

Executa uma determinada função de x em x milisegundos

Por exemplo, para apresentar um relógio digital vamos ter de executar uma função por ex. a cada segundo, que vai atualizar a hora.

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

Existem plugins para animações que podemos incluir no projeto. Por exemplo o animate
https://animate.style/

Podemos pegar no exercicio do setTimeout e alterá-lo de forma a que a mensagem desaparece com uma animação de *fade out*.

```html
 <div class="msg bg-secondary text-white animate__animated">
      <p class="text-center">Obrigado pela subscrição</p>
</div>
    
```

```js
function hideMessage () {
	let msg = document.querySelector('.msg');
	  //welcome.style = 'display:none';
	  welcome.classList.add ('animate__fadeOutUp')
}
```

>[!tip] Custom
> Podemos alterar algumas propriedades das animações animate como por exemplo a duração:   `animation-duration: 0.5s`
