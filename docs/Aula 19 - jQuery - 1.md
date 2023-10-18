# O que é?

A javascript library on top javascript to deliver more powerful functionalities with simplified expressions.

some jquery plugins:

colorbox.js - para mostrar como poderiam fazer uma light box
hook.js - pull to refresh plugin
tooltipster - more powerful tooltips
unslider - to build slider effects
magnetic popup - to build great photo pop up screens
typeahead.js - tries to predict the words on searching inputs

# Instalação

### local ou remota

- local garante a utilização de uma determinada versão 
- remotamente podermos usar jquery-latest.js para ligar sempre a versão mais recente
- remotamente o servidor pode ser mais rápido
- remotamente pode estar já em cache pela visita de outros sites, pelo que o nosso é carregado mais rápido.

LOCAL: 
`<script type="text/javascript" src="jquery.min.js"\>\</script\>`

REMOTA: 
`<script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"\>\</script\>`

# Selecionar um elemento

- Pegar no exemplo do Blog, apagar input e criar 2 posts

`$("elemento") -> $("div”)`

`$("#elemento_id)`

`$(".class_id)`

`$(".post h3”) `-\> elementos `h3` dento de elemento com class `post`

```html

  <body>
  
    <h2>Blog Posts</h2>
    <div class="postList">
      <div class="post">
        <h3>Lorem Ipsum</h3>
        <p>Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words</p>
        
        <p>13 de Janeiro 2021</p>
      </div>
      <hr />
      <div class="post">
        <h3>Lorem Ipsum</h3>
        <p>Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. Richard McClintock, a Latin professor at Hampden-Sydney College in Virginia, looked up one of the more obscure Latin words</p>
        
        <p>13 de Janeiro 2021</p>
      </div>

      <h3><a href="">Next theme is about Lorem</a></h3>
    </div>


    <script type="text/javascript" src="jquery/jquery-3.6.0.js"></script>
    <script type="text/javascript" src="scripts/moment-with-locales.js"></script>
    <script type="text/javascript">

      // JQuery selectors examples

      $(".post").css("color", "blue"); // equivalente ao document.getElementsByClass("post")[0]

     // $("#nome_do_id") - selection of an id
     $("h3").css("color", "gray");

     $(".post h3").css("color", "red");


     // Altera html (.text - aletra texto)
     $("h2").html("Posts about Ipsum");


     // Change an attribute
     $("a").attr("href", "https://www.publico.pt");

     // Esconder / mostrar elemento
     $("a").hide();

     // Add click to elements, with a callback function
     $(".post h3").click(function(){
        //$("a").toggle();
        $("h3 a").fadeToggle(400, function() {
          $(this).text("I've changed the link description");
        });
     })



    </script>
  </body>

```

# Eventos (ex. click) 

```js

   $(".post h3").click(function(){
      alert("Post clicked!")
    });

```

# Alterar/Obter propriedade de vários elementos clicados

Por exemplo mostra o HTML da DIV clickada

```js
$("div").click(function(){
      alert($(this).html());
    });
```

# Alterar um elemento
-------------------


```js
	$("elemento").html("novo conteúdo");

	// devolve o conteúdo actual HTML do elemento.
	$("elemento").html()
	
	// Altera html (.text - aletra texto)
	$("h2").html("Posts about Ipsum");
```

# Alterar um atributo

ex. o href dos links

```js
 $("a").attr("href","http://www.lsd.pt");
```

# Alterar uma propriedade CSS de elementos


```js
	$("elemento").css("propriedade", "valor")

	$("elemento").css("propriedade") -\> ontem valor corrente

	$(".post").css("color", "blue")
```

# Esconder/Mostrar um elemento 

```js
 $("a").hide(); // show, toggle
```


```js
// fadeIn, fadeOut e fadeToggle
// duration in milliseconds or phrases (slow, fast, )
$("div").fadeOut/In (duration, callback)

// Add click to elements, with a callback function
     $(".post h3").click(function(){
        //$("a").toggle();
        $("h3 a").fadeToggle(400, function() {
          $(this).text("I've changed the link description");
        });
     })
```

# Animations
```javascript
$("div").animate ( properties, time, callback)

$("div").animate ({
 width:100px,
 height: 100px,
 ///borderRadius, marginLeft, marginTop, etc
}, 1500)
```

Para animações que usem color e background color tem-se de adicionar o JQuery UI

<http://code.jquery.com/ui/>

```js
// 1. COLOCAR top: 30% na class .box 
.box {
  top: 30%;
  opacity: 0
}

 // 2. animate section ------------
 var newHeight = $(document).height()/2 - 150;

  $(".box").animate({
    opacity:1,
    top: newHeight
  }, 700, "swing");
  // ---------------animate section 


```

# Exercício NEWS (grid com mais info)

```html
<!doctype html>
<html>

<head>
    <title>JQuery More Info</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet"
        integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@100;300&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" />

    <style type="text/css">
        * {
            font-family: Helvetica;
        }

        .cell {
            position: relative;
            background-size: cover;
            background-position: center;
            height: 300px;
        }

        .cell1 {
            background-image: url("./images/news1.png");
        }

        .cell2 {
            background-image: url("./images/news2.png");
        }

        .cell3 {
            background-image: url("./images/news3.png");
        }

        .maisInfo {
            background-color: rgba(0, 0, 0, 0.5);
        }
    </style>
</head>

<body>
    <div class="container d-flex vh-100 ">
        <div class="align-self-sm-center w-100 animate__animated animate__fadeInDown animate__faster">
            <h1 class="display-2 fw-bold text-secondary mx-0">NEWS</h1>
            <div class="row g-0">
                <div class="cell1 cell col-sm">
                    <div class="maisInfo h-100 w-100 position-absolute top-0 start-0 text-center">
                        <button class=" btn btn-dark btn-lg mt-5">more</button>
                    </div>
                </div>
                <div class="cell2 cell col-sm mx-sm-2 my-2 my-sm-0">
                    <div class="maisInfo h-100 w-100 position-absolute top-0 start-0 text-center">
                        <button class=" btn btn-dark btn-lg mt-5">more</button>
                    </div>
                </div>
                <div class="cell3 cell col-sm">
                    <div class="maisInfo h-100 w-100 position-absolute top-0 start-0 text-center">
                        <button class=" btn btn-dark btn-lg mt-5">more</button>
                    </div>
                </div>
            </div>
        </div>

    </div>

    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-kenU1KFdBIe4zVF0s0G1M5b4hcpxyD9F7jL+jjXkk+Q2h455rYXK/7HAuoJl+0I4"
        crossorigin="anonymous"></script>
    <script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"></script>
    <script type="text/javascript">

        $(document).ready(function () {

            $(".maisInfo").hide();

            $(".cell").mouseenter(onMouseEnter);
            $(".cell").mouseleave(onMouseLeave);

            function onMouseEnter() {
                // apresentar a div maisInfo que está dentro da cell que tem o rato
                $(this).find(".maisInfo").fadeIn("fast");
            }

            function onMouseLeave() {
                // esconder o maisInfo
                $(this).find(".maisInfo").fadeOut("fast");
            }

        });

    </script>
</body>

</html>
```

