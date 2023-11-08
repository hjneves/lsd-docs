A animação de elementos html com recurso a css é conseguida através das propriedades `animation` e `transition`.

Transições
-   Apenas move um elemento de um estado inicial para um final. Não existem passos intermédios.
-   Requer um trigger (por ex. hover) para iniciar e é executada apenas uma vez
-  Aplica a transição com o trigger mas volta ao estado inicial quando o trigger termina

Animações
-   Avança de um estado inicial para um final, mas pode ter passo intermédios.
-   Não necessita de trigger e pode executar em loop
-   Pode executar em diversas direções, normal, inversa, alternada
-   Melhor opção para animações de movimento mais complexas.

# Transition

As transições são uma forma simples de animar uma ou várias propriedades css de um estado inicial para um estado final.

Podemos por exemplo usar uma transição para mudar a cor de fundo de uma caixa quando o utilizador passa o rato por cima, ou seja, em `:hover`.

```css
<div class="box"></div>
```
```css
.box {
  width: 150px;
  height: 150px;
  background: #000000;
  margin-top: 20px;
  margin-left: auto;
  margin-right: auto;
  transition: background-color, border-radius 400ms ease-out;
}

.box:hover {
  background-color: #aaaaaa;
  border-radius: 8px;
  cursor: pointer;
}
```

A propriedade `transition`é definida nas regras css do elemento, indicando:
	*propriedade a animar - duração da transição - curva de animação*
Em `hover` como temos uma alteração da propriedade que está sujeita a transição (background-color) a mudança é feita segunda a transição definida.

Elemento normal
![[Pasted image 20231024112714.png|260]]  

Elemento em `:hover`
![[Pasted image 20231024112755.png|300]]

>[!tip] Nota
>Se colocarmos `all` como propriedade a animar na regra de `transition`,  todas as alterações verificadas nas propriedades vão ser animadas 

# Animation & @keyframes

Quando queremos realizar animações mais complexas que envolvam mais estados intermédios entre o início e o fim da animação temos de recorrer à propriedade `animation` e à regra `keyframes`

O principal componente das animações css são os `@keyframes` a regra que define a estrutura da animação. `@keyframes` podem ser vistas como as diferentes fases ao longo do tempo pelas quais a animação passa, onde em cada uma delas podem estar diferentes propriedades css.

Para que a animação funcione as `@keyframes` devem estar ligada a uma `animation`num determinado seletor.

Por exemplo, se quisermos fazer um determinado elemento pulsar, indefinidamente

```html
<div class="pulser"></div>
```
```css
.pulser {
  width: 30px;
  height: 30px;
  background: yellowgreen;
  border-radius: 50%;
  animation: pulse 1s ease infinite alternate;
}

@keyframes pulse {
  0% {
    opacity: 0;
  }
  100% {
    transform: scale(1.4);
  }
}
```

Foi definida na classe .pulser uma animation com a @keyframes pulse. Vai ser executada durante 1 segundo, de forma infinita e alternada.
A estrutura da animação parte (0%) com uma opacidade a 0 e termina (100%) com uma transformação de escala do elemento.

A forma como foi definida a animation tem por base uma forma abreviada de especifiacr diversos parâmetros que neste caso seriam:

```
animation-duration: 1s;
animation-timing-function: ease;
animation-iteration-count: infinite;
animation-direction: alternate;
```

# Plugin animate

https://animate.style/

Animate e um repositório de animações css pré-definidas que podemos incluir numa página e utilizar nos nossos elementos. 

Para instalar basta incluir o link para o ficheiro css:
```html
  <link
rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
  />
```

Para utilizar basta adicionar duas classes aos elementos: uma classe genérica `animate__animated` e a classe correspondente à animaçã pretendida,  por ex. `animate__fadeIn`.


Neste exemplo o heading aparece com uma animação de fadein:
```html
<div class="animate__animated animate__fadeIn">
  <h1>Welcome</h1>
</div>
```

Podemos alterar algumas propriedades com recurso às propriedades de animação css que temos disponíveis, por ex. o  tempo da animação `animation-duration: 0.5s`

Ver mais sobre [animações](https://web.dev/learn/css/animations).



