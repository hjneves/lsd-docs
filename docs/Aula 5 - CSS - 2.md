CSS is about styling you content built with html

CSS - Cascade Style sheet

**FONTS**
---------

****

tenta usar a fonte mais à esquerda, caso não consiga avança pela direita até à fonte genérica

```css
p {
    font-family: "Times New Roman", Georgia, Serif;
}
```

```css
font-weight: bold
font-style: italic
text-decoration: underline
```

`font-size: 150%` (em % e relativo ao tamanho do elemento parent)

`font-size: 26px` (valor absoluto, valor default são 16px)

`font-size: 1.2em `(recomendados para o zoom funcionar bem - 16px = 1em - relativo ao elemento pai)

**FONTES REMOTAS - Google Fonts**
---------------------------------

Criar colecção no google fonts

Usar um link para as fontes definidas na coleção google fonts

```css
<link href='https://fonts.googleapis.com/css?family=Roboto:500|Lato' rel='stylesheet' type='text/css' />
```

**FONTES LOCAIS **
------------------

With the @font-face rule, web designers do no longer have to use one of the "web-safe" fonts.

In the new @font-face rule you must first define a name for the font (e.g. myFirstFont), and then point to the font file.

**Tip**: Use lowercase letters for the font URL. Uppercase letters can give unexpected results in IE!

Criar as variações como fontes diferentes

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

**OUTROS SELECTORES**
---------------------

**Aplicar CSS a elementos dentro de outro elemento**
----------------------------------------------------

```css
  div p {
      color: blue;
    }

```

**Aplicar CSS a elementos dentro de uma classe ou ID**
------------------------------------------------------

```css
  #menu p {
      color: blue;
    }
```



```html


  <div id="menu">
    <p>About | Products | Services | Support | Contacts</p>
  </div>

  <div>
    <p>About the company ....</p>
  </div>
 
   <p>Our products are the result of a deep  ....</p>

```

**Aplicar CSS a um elemento (neste caso um parágrafo) com uma determinada classe**
----------------------------------------------------------------------------------

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

**
**

**a:link (links não visitados) e a:visited (links visitados)**
--------------------------------------------------------------

```css
  a:link {
      color: green;
    }
```

```css
  a:visited {
      color: gray;
    }
```

**
**

**div:hover (cria estilo sobre div quando tem o rato por cima)**
----------------------------------------------------------------

**menus**

**add info skimming**

```css
    div:hover {
      margin-left: 20px;
    }

    a:hover {
      border-bottom: 2px gray solid;
    }
    
    
```

**
**

**div:hover (mostra imagem)**
-----------------------------

```css

<!doctype html>
<html>
<head>
    <title>CSS Stuff 2</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link href="https://fonts.googleapis.com/css?family=Roboto&display=swap" rel="stylesheet">

    <style type="text/css">

        body {
            background-color: lightblue;
            font-size: 100%;
            font-family: Helvetica;
            margin: 0;
        }

        @font-face {
            font-family: Girassol;
            src: url('fonts/Girassol/Girassol-Regular.ttf');    
        }

        @font-face {
            font-family: RobotoBold;
            src: url('fonts/Roboto/Roboto-Bold.ttf');
        }

        #wrapper {
            max-width: 600px;
            height: 100vh;
            
            /* regras de margin à direita e esquerda*/
            margin-left: auto;
            margin-right: auto;

            /* Regra sistematizada [top bottom] [left right]*/
            margin: 0 auto;

            /* Regra sistematizada [top] [right] [bottom] [left]*/
            margin: 0 auto 0 auto;
            background-color: white;

            padding: 10px;
        }


        h1, h2 {
            color: #aaaaaa;
            background-color: white;
            font-family: "Times New Roman", Georgia, Serif;
            font-style: italic;
        }
/*
        h2 {
            color: #ff0000;
        }
*/
        p {
            color: orange;
            font-size: 1.2em;
        }

        .thumbnail {
            width: 100px;
            height: 100px;
            /* regra sistematizada do border*/
            border: 2px black solid;

            /* Regras individuais do border*/
            border-width: 2px;
            border-color: black;
            border-style: solid;

            border-radius: 50px;
            overflow: hidden;

        }
        
        .thumbnail img {
            display: none;
        }

        .thumbnail:hover > img{
            /*border: 4px black solid;*/
            display: block;
        }

        .thumbnail p {
            font-family: 'Girassol', sans-serif;
            font-size: 2em;
            text-align: center;
            position: absolute;
        }

        .thumbnail img {
            height: 100px;
        }

        .center {
            text-align: center;
        }

        h2.center {
            border: 1px grey solid;
        }

        a:visited {
            color: gray;
        }

        a:link {
            color: green;
            text-decoration: none;
        }

    </style>    
</head>

<body>
    <div id="wrapper">
        <div class="thumbnail">
            <p>Hello</p>
            <img src="images/rusteze.jpg">
        </div>        
        <div class="thumbnail">
            <p>Winner</p>
            <img src="images/rusteze.jpg">
        </div>        

        <div class="thumbnail">
            <p>Thanks</p>
            <img src="images/rusteze.jpg">
        </div>



        <p>
            <a href="http://www.pixar.com">This is a link</a>
        </p>
        <p>
            <a href="http://www.apple.com">This is another link</a>
        </p>

        <div>
            <p>
                
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Feugiat nibh sed pulvinar proin gravida. Pellentesque nec nam aliquam sem et tortor consequat id porta. Fusce id velit ut tortor pretium viverra. Dignissim suspendisse in est ante in nibh. Elementum curabitur vitae nunc sed. Sed tempus urna et pharetra pharetra massa. Hendrerit dolor magna eget est. Gravida arcu ac tortor dignissim convallis aenean. Varius sit amet mattis vulputate enim. Senectus et netus et malesuada fames ac turpis. A pellentesque sit amet porttitor eget dolor morbi non arcu. Nisl suscipit adipiscing bibendum est. Malesuada fames ac turpis egestas maecenas pharetra convallis. Facilisis magna etiam tempor orci.

Placerat vestibulum lectus mauris ultrices eros in cursus turpis massa. Laoreet sit amet cursus sit amet dictum sit. Felis donec et odio pellentesque diam volutpat. Urna id volutpat lacus laoreet non curabitur gravida arcu. Pulvinar neque laoreet suspendisse interdum consectetur libero id. Aliquam eleifend mi in nulla posuere. Rhoncus dolor purus non enim praesent

            </p>

            <h2>INFO</h2>


        </div>


        <h2 class="center">Heading text</h2>
        <p class="center">This is a paragraph</p>



    </div>
    


</body>
</html>

```

Grid's
------

* Pode-se usar `float:left` repetidamente, ele val alinhando à direita do ultimo elemento floated.
* Usar o `display: inline-block`​ neste caso atenção que ele usa espaços e quebras de linha entre os elementos.
* Mais usados: Usar o `​display: grid`​ semelhante ao flexbox mas mais flexível. É bi-dimensional (exemplo source)
* Mais usados: User o display `display: flex`​ (mais recente)

📌Atenção:

O **`box-sizing: border-box` **permite que o tamanho width e height incluam a border e o padding

 Flexbox is made for one dimensional layouts and Grid is made for two dimensional layouts.

FAVICON

[http://realfavicongenerator.net](http://realfavicongenerator.net/)

**FLEX**

```html
<!doctype html>
<html>
<head>
    <title>My CSS Page</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link href='https://fonts.googleapis.com/css?family=Roboto:500|Lato' rel='stylesheet' type='text/css' />

    <style type="text/css">

			#wrapper {
				width: 80%;
				margin: 0 auto;
			}

			.boxFloat div {
				width: calc(100%/3);
				height: 80px;
				background-color: green;
				float: left;
			}

			.clear {
				clear: both;
			}

			.borders div {
				border: 1px solid black;
				box-sizing: border-box;
			}


			.boxInline div {
				width: 25%;
				height: 80px;
				background-color: orange;
				display: inline-block;
			}

			.boxGrid-area {
				display: grid;
				grid-template-columns: 25% 25% 25% 25%;
				grid-template-rows: 100px;
				grid-gap: 1px;
			}

			.boxGrid-area div {
				background-color: #444;

			}

      .flex-container {
        /* We first create a flex layout context */
        display: flex;
        
        /* Then we define the flow direction 
           and if we allow the items to wrap 
         * Remember this is the same as:
         * flex-direction: row;
         * flex-wrap: wrap;
         */
        flex-flow: row wrap;
        
        /* Then we define how is distributed the remaining space */
        justify-content: space-around;
        
        padding: 0;
        margin: 0;
        list-style: none;
      }
      
      .flex-item {
        background: tomato;
        padding: 5px;
        flex: auto /* grow: 1 shrink: 1 basis: auto */
        height: 150px;
        margin-top: 10px;
        line-height: 150px;
        color: white;
        font-weight: bold;
        font-size: 3em;
        text-align: center;
      }

    </style>


</head>


<body>

  

</body>

</html>
```

```html
<div id="wrapper">
	
		<h2>Grid systems</h2>

		<p>Using floats</p>
		<div class="boxFloat">
			<div>Cell1</div>
			<div>Cell2</div>
			<div>Cell3</div>
		</div>

		<div class="clear"></div>

		<p>Using floats - with borders</p>
		<div class="boxFloat borders">
			<div>Cell1</div>
			<div>Cell2</div>
			<div>Cell3</div>
			<div>Cell4</div>
		</div>

		<div class="clear"></div>

		<p>Using inline-block</p>
		<div class="boxInline">
			<div>Cell1</div>
			<div>Cell2</div>
			<div>Cell3</div>
			<div>Cell4</div>
		</div>


		<p>Using css Grid</p>
		<div class="boxGrid-area">
			<div>Cell1</div>
			<div>Cell2</div>
			<div>Cell3</div>
			<div>Cell4</div>
		</div>

<ul class="flex-container">
  <li class="flex-item">1</li>
  <li class="flex-item">2</li>
  <li class="flex-item">3</li>
  <li class="flex-item">4</li>
  <li class="flex-item">5</li>
  <li class="flex-item">6</li>
</ul>



	</div>
```