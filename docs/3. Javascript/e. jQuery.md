## O que é?

A javascript library on top javascript to deliver more powerful functionalities with simplified expressions.

some jquery plugins:

colorbox.js - para mostrar como poderiam fazer uma light box
hook.js - pull to refresh plugin
tooltipster - more powerful tooltips
unslider - to build slider effects
magnetic popup - to build great photo pop up screens
typeahead.js - tries to predict the words on searching inputs

## Instalação

### local ou remota

- local garante a utilização de uma determinada versão 
- remotamente podermos usar jquery-latest.js para ligar sempre a versão mais recente
- remotamente o servidor pode ser mais rápido
- remotamente pode estar já em cache pela visita de outros sites, pelo que o nosso é carregado mais rápido.

LOCAL: 
`<script type="text/javascript" src="jquery.min.js"\>\</script\>`

REMOTA: 
`<script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"\>\</script\>`

## Selecionar um elemento

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

## Eventos (ex. click) 

```js

   $(".post h3").click(function(){
      alert("Post clicked!")
    });

```

## Alterar/Obter propriedade de vários elementos clicados

Por exemplo mostra o HTML da DIV clickada

```js
$("div").click(function(){
      alert($(this).html());
    });
```

## Alterar um elemento

```js
	$("elemento").html("novo conteúdo");

	// devolve o conteúdo actual HTML do elemento.
	$("elemento").html()
	
	// Altera html (.text - aletra texto)
	$("h2").html("Posts about Ipsum");
```

## Alterar um atributo

ex. o href dos links

```js
 $("a").attr("href","http://www.lsd.pt");
```

## Alterar uma propriedade CSS de elementos

```js
	$("elemento").css("propriedade", "valor")

	$("elemento").css("propriedade") -\> ontem valor corrente

	$(".post").css("color", "blue")
```

## Esconder/Mostrar um elemento 

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

## Animations
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

