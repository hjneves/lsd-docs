Vamos começar por ver como é a estrutura de uma página html e as principais tags.
### Header

```html
<!DOCTYPE html>
<html>

<head> <!--comentário html: secção head da página web -->
  <title> o que aparece no tab do browser </title>
  <!-- meta tags incluem informação sobre propriedades do documento -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="A blurb to describe the content of the page appears here" >
  <style> 
    /* comentário css: alguns estilos com css */
  </style>

</head>
```

### Body

```html
<body> <!-- corpo da página web, conteúdo efectivo da página -->
     <div> uma divisão da página web</div>
     <p> um parágrafo </p>
     <p><a href = "www.ardozia.com">Um link dentro de um parágrafo</a></p>
</body>

```

`index.html` - por convenção a página raiz de um site web. 
Ou seja ao abrir o endereço `www.example.com` estamos o servidor web vai tentar encontrar o ficheiro `index.html` para abrir.  

### DIV’s e semântica em HTML5

A tag `div` é a base da organização estrutural de uma página html. Todo o conteúdo deverá estar inserido em `div´s`. As `div`podem conter outras `div`, criando uma estrutura hierárquica de pais para filhos, onde a div que engloba toda a página normalmente designa-se de wrapper e na zona mais específica temos os blocos de texto e imagens. 

Por exemplo, um parágrafo inserido numa `div`
`<div><p>uma divisão da página web<p></div>`.  

Na imagem seguinte uma estrutura genérica de uma pagina web, usando tags html5. Estas tags são `div's` com uma determinada semântica associada que é reconhecida em termos de SEO.

![[Pasted image 20221115190049.png]]
## Header Tags

As tags de heading reconhecidas são 
`<h1> ..... <h6>` 
Normalmente encontramos numa página um `<h1>` alguns `<h2>` e `<h3>`.  

## Parágrafos

Se tentarmos escrever texto diretamente nas `<div>` verificamos que não se consegue separar linhas e os espaços são ignorados.

A tag `<p>` de parágrafo, deverá ser usada quando escrevemos texto, ela coloca um espaçamento na vertical entre ele e efetua uma quebra de linha.

Usar `<br />` para quebrar linha sem parágrafo. 

`<hr />`  horizontal rule criar uma linha horizontal. 

## Tags de decoração

`<strong>` texto a bold. 
`<em> `texto em itálico , `em` vem de emphasis. 
`<u>` texto sublinhado. 
`<strike>` texto rasurado. 

## Lista não ordenada

```html
<ul>
    <li> item de lista </li>
    <li> item de lista </li>
</ul>
```

>**Nota**
>Vamos verificar que as listas são muito usadas na estrutura e semântica dos menu de navegação dos sites
## Lista ordenada

```html
<ol> 
    <li> item de lista </li>
    <li> item de lista </li>
</ol>
```

## Imagens

```html
<img src="images/passaro.jpg" /> <!--self closed tag e um ficheiro local, tem por base a directoria do ficheiro html que a contém -->
<img src="images/passaro.jpg" width=200/> <!--tamanho proporcional com base na largura -->
<img src="images/passaro.jpg" height=200/> <!--tamanho proporcional com base na altura-->
<img src="images/passaro.jpg" width=200 height="500"/> <!--tamanho definido em altura e largura, pode distorcer-->
```

A tag de imagem `<img>` é uma self-closed tag e usa o atributo `src` para indicar o caminho para a imagem. No exemplos acima a imagem está a ser indicada através de um caminho relativo. Também se pode indicar uma imagem remota através de um endereço http.

```html
<img src="https://img.freepik.com/fotos-premium/um-passaro-preto-com-bico-amarelo-voa-no-ceu_899894-12288.jpg" alt="pássaro escuro a voar"/>
```

O atributo `alt` indica aos motores de pesquisa que imagem está a ser apresentada, tonando-se importante que esteja preenchida em todas as tags `<img>` relevando para SEO. 

>**Online Image Generators**
Existem serviços online que permitem aceder a imagem dummy com um tamanho que queremos, como por exemplo o [Lorem Picsum](https://picsum.photos) ou o [dummy Images](https://dummyimage.com/)

## Artigos

Tag html5 que permite organizar conteúdos de notícias, posts, ..

```html
<article>
  <h1>Google Chrome</h1>
  <p>Google Chrome is a free, open-source web browser developed by Google, released in 2008.</p>
</article>
```

## Forms

Os forms são as secções de uma página que podem receber dados do utilizador. Existem vários tipos de tags que podem ser usadas para recolher informação, campo de input, text area, check box, radio button, drop down box e button.

O evento de `submit` desencadeado por um botão (ex. tag input do tipo submit) recolhe todas as informações que estão preenchidas pelo utilizador, valida-as no cliente e envia-as para serem tratadas no servidor (validações e acções dinâmicas)

```html
<form action"web site para onde vai depois do submit">
    <input type="text" value="exemplo" /> - cria uma campo de input preenchido com exemplo
    <input type="text" placeholder="escrever aqui ..." /> - cria uma campo com um hint, desaparece quando se escreve
    <input name="email" type="email" value="exemplo@example.com" /> - cria uma campo de input, tipo email

    <label for="email">Email:</label>  -> liga uma label ao campo de nome email
    <input name="email" type="email" value="exemplo@example.com" /> - cria uma campo de input, tipo email

    <textarea>Conteúdo de uma area de escrita</textarea>
    
    <select> é uma drop down box
          <option>opção1</option>
          <option>opção2</option>
    </select>

    <input type="checkbox" />João <!--- botões radio -->
    <input type="checkbox" />José

    <input type="radio" name="cor" />Verde  <!-- botões checkbox -->
    <input type="radio" name="cor" />Azul

     <input type="submit" value="Click here"/> 
     <!--botão de submit
    Importante: submete o form (GET ) usando os parametros identificados com name nas tags input
     o valor de cada tag enviada é definido pelo parámetro value ou pelo utilizador -->

</form>
```

## Links

```html
<a href="http://www.google.com">Google</a> link externo é necessário colocar http
<a href="helloworld.html">Hello </a> linkintero

<a name="top" /> achor para ser referenciado

<a href="#top">Back to top</a>

Links especiais
<a href="mailto:friend@something.com?subject=Great%20news">Some text</a>
```

## Tabelas

```html
<table>
    <tr><th>Nomes</th><th>Cor</th><th>Material</th></tr>
    <tr><td>cadeira</td><td>branca</td><td>madeira</td></tr>
</table>

<th> column header
<tr> table row
<td> column data item
```

## Entidades html

Por vezes a utilização de caracteres reservados para poderem ser utilizados têm de ser substituidos por códigos ou nomes de entidades.

[http://www.w3schools.com/html/html\_entities.asp](http://www.w3schools.com/html/html_entities.asp)

Por exemplo o non-breaking space (&nbsp). Pode ser usado para apresentar uma velocidade mantendo sempre o valor e a unidade juntos (10 km/h), ou seja a linha nunca vai quebrar entre o 10 e o km/h. 
## iframe

Permite embeber um documento externo no documento atual. Usado por ex. para embeber videos do Youtube.

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/A5AV5HAKjh0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
```

## Media em html5

### Audio

Tanto na tag de audio como na de video, é necessário indicar uma source, ou seja a localização para o ficheiro de media que vai ser apresentado ou reproduzido.

* Site musicas e sfx demo: [Bensound](https://www.bensound.com/royalty-free-music). 


```html
<audio controls loop muted preload autoplay>
  <source src="audio/4estacoes.ogg" type="audio/ogg">
  <source src="audio/4estacoes.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>
```

Por questões de *user experience* alguns browsers não aceitam o autoplay no carregamento de uma página (ex. chrome)

Ver mais sobre [web audio](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide)

### Vídeo

#review
* como fundo usar de forma a tipografia ser legível. 
* sem som (ver autoplay). 
* `autoplay` só funciona bem no refresh com muted=true - protecção dos browers para páginas ruidosas. 
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


## Icones

Existem algumas livrarias de ícones disponibilizadas que podemos utilizar e que têm por base elementos vetoriais disponibilizados através da importação de um ficheiro css externos.

Os [Bootstrap Icons](https://icons.getbootstrap.com)  são um exemplo de uma destas livraria. 
Para importar temos de incluir o seguinte link:
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.1/font/bootstrap-icons.css">
```

Para utilizar um ícone é necessário conhecer o nome dele através da [documentação](https://icons.getbootstrap.com/#icons) e depois usá-lo no nome da classe de um elemento `<i>`. 
```html
<i class="bi-alarm"></i>
```

Font Awesome é uma outra livraria muito utilizada.

## Botão vs. link

Por vezes encontramos botões e links formatados em css de forma muito semelhante, no entanto a utilização de um ou de outro difere conforme o objetivo pretendido.

**Botões**

* implica uma acção que altera conteúdos no site (CTA), compras, registos, pesquisas

**Links**

* relacionado com navegação

### Tipos de botões 

Podemos definir um botão usando a tag `<button>` ou a tag `<input>` com o seguinte atributo  `type="submit"`. 
Ambos permitem submeter informação de um form (type submit) mas a tag `<button>` tem uma mais fácil legibilidade e com é uma tag com conteúdo tem mais flexibilidade em termos de formatação. Podemos por exemplo colocar uma imagem dentro do botão.

```html
<form>
	...
	<button class="btnBuy">COMPRAR</button>
</form>
```

No caso do botão com a tag `<input>` para além do tipo submit existem outros que podem ser criados conforme o tipo:

Atributo `type`:

* `button` - The button is a clickable button. 
* `submit` - The button is a submit button (submits form-data). 
* `reset` - The button is a reset button (resets the form-data to its initial values). 