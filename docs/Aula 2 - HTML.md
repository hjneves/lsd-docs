codepen.com
para enviar exemplos e tirar dúvidas

CANIUSE.com 
para validar compatibilidade das instruções CSS3 nos diversos browsers e versões


Instalações

Visual Studio Code

Google Chrome 

Apresentar HTML 

Ver source de sites (example.com)

exemplo de tags, nesting - `<p> Um pedaço de texto <span> em html </span></p>`

Começar por experimentar escrever directamente no ficheiro HTML

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

**Sobre o body**

```html
<body> corpo da página web, conteúdo efectivo da página
     <div> uma divisão da página web</div>
     <p> um parágrafo </p>
     <p><a href = "www.ardozia.com">Um link dentro de um parágrafo</a></p>
</body>

```

`index.html` - por convenção a página raiz de um site web

**DIV’s e SEMÂNTICA em HTML5**

Bloco de conteudo html, extremamente utilizado para organizar estrutura dos sites

`<div> uma divisão da página web</div>`

![[Pasted image 20221115190049.png]]
**Header Tags**

`<h1> ..... <h6>` a partir daqui não reconhece

em paginas reais normalmente temos um H1 alguns h2 e h3

**Paragraphs**

Coisas estranhas acontecem quando digitamos texto sem tags.

- não separa linhas 

- ignora espaços

`<p>` usar sempre que escrevemos texto - coloca padding - é um parágrafo

usar `<br />` para quebrar linha sem parágrafo

`<hr />` horizontal rule

**Text Decoration/Formating**

`<strong>` texto a bold html5, dantes usava-se o \<b\>

`<em> `texto em itálico , vem de emphasis

`<u>` texto sublinhado

`<strike>` texto rasurado

**Listas não ordenadas - bullet points**

```html
<ul>
    <li> item de lista </li>
    <li> item de lista </li>
</ul>
```

**Lista ordenada, coloca números nos items**

```html
<ol> 
    <li> item de lista </li>
    <li> item de lista </li>
</ol>
```

**IMAGENS**

obter uma imagem da web

```html
<img src="images/passaro.jpg" /> <!--self closed tag e um ficheiro local, tem por base a director do index.html -->
<img src="images/passaro.jpg" width=200/> <!--tamanho proporcional com base na largura -->
<img src="images/passaro.jpg" height=200/> <!--tamanho proporcional com base na altura-->
<img src="images/passaro.jpg" width=200 height="500"/> <!--tamanho definido em altura e largura, pode distorcer-->
```

ARTIGOS

Permitem organizar conteudos de noticas, posts, HTML5

```html
<article>
  <h1>Google Chrome</h1>
  <p>Google Chrome is a free, open-source web browser developed by Google, released in 2008.</p>
</article>
```

**FORMS**

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

**LINKS**

```html
<a href="http://www.google.com">Google</a> link externo é necessário colocar http
<a href="helloworld.html">Hello </a> linkintero

<a name="top" /> achor para ser referenciado

<a href="#top">Back to top</a>

Links especiais
<a href="mailto:friend@something.com?subject=Great%20news">Some text</a>
```

**TABELAS**

```html
<table>
    <tr><th>Nomes</th><th>Cor</th><th>Material</th></tr>
    <tr><td>cadeira</td><td>branca</td><td>madeira</td></tr>
</table>

<th> column header
<tr> table row
<td> column data item
```

**HTML Entities**

Special code that bowser replaces with a character

[http://www.w3schools.com/html/html\_entities.asp](http://www.w3schools.com/html/html_entities.asp)

**iFrame**

```html
<iframe align="right"  src=video youtube></iframe> src remotas é  necessário ficheiro estar também remoto


```