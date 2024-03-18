# O que é?

A javascript library on top of javascript to deliver more powerful functionalities with simplified expressions.

some jquery plugins:

- [ScrollMagic](https://scrollmagic.io) - efeitos com o scroll na página 
- hook.js - pull to refresh plugin 
- tooltipster - more powerful tooltips 
- [Magnific popup](https://dimsemenov.com/plugins/magnific-popup/) - to build great photo pop up screens 
- typeahead.js - tries to predict the words on searching inputs 

# Instalação

## local ou remota

- local garante a utilização de uma determinada versão 
- remotamente podermos usar jquery-latest.js para ligar sempre a versão mais recente
- remotamente o servidor pode ser mais rápido
- remotamente pode estar já em cache pela visita de outros sites, pelo que o nosso é carregado mais rápido.

LOCAL: 
`<script type="text/javascript" src="jquery.min.js"\>\</script\>`

REMOTA: 
`<script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"\>\</script\>`

# Selecionar um elemento

```js
$("elemento") -> $("div”)`
$("#elemento_id)
$(".class_id)
$(".post h3”) // elementos `h3` dento de elemento com class `post`
```

```html
      <div class="container">
        <h2>Lista de trabalhos</h2>
        <div class="workList d-flex flex-column gap-3">
            <div class="work d-flex column-gap-3">
                <img src="https://picsum.photos/id/23/200" />
                <div class="">
                    <p class="fs-5 fw-bold">Desenho de fonte</p>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
                    <p class="fs-6">Dezembro 2023</p>
                    <p role="button" class="likes" data-liked="no">
                        <i class="bi bi-heart-fill"></i>
                        <span>6</span>
                    </p>
                </div>
            </div>
            <div class="work d-flex column-gap-3">
                <img src="https://picsum.photos/id/111/200" />
                <div class="">
                    <p class="fs-5 fw-bold">Plugin Wordpress</p>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.dolor sit amet, consectetur adipiscing.
                    </p>
                    <p class="fs-6">Janeiro 2023</p>
                    <p role="button" class="likes" data-liked="no">
                        <i class="bi bi-heart-fill"></i>
                        <span>10</span>
                    </p>
                </div>

            </div>
            <div class="work d-flex column-gap-3">
                <img src="https://picsum.photos/200" />
                <div class="">
                    <p class="fs-5 fw-bold">Concepção de logotipo</p>
                    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.Lorem ipsum dolor sit amet, consectetur
                        adipiscing elit.</p>
                    <p class="fs-6">Dezembro 2023</p>
                    <p role="button" class="likes" data-liked="no">
                        <i class="bi bi-heart-fill"></i>
                        <span>230</span>
                    </p>
                </div>

            </div>
        </div>
    </div>
```
```js
  // JQuery selectors examples

   // Change all works date
	$('.work div p:nth-child(3)').text("Outubro de 2023")

	//$('.work div p:nth-child(3)').css("color","darkred")

	$('.work div p:nth-child(3)').toggleClass('text-secondary')

	$('img').attr('src', 'https://picsum.photos/200')

	//$('img').hide()

	// eventos
	$('img').on('click', function () {
		const id = Math.floor(Math.random(1) * 200) + 1
		$(this).attr('src', 'https://picsum.photos/id/' + id + '/200')
		//$(this).attr('src','https://picsum.photos/id/200')
	}) +

	$('.likes').on('click', function () {
		$(this).find('i').toggleClass('text-danger')

		let nrLikes = $(this).find('span').text()
		// aumenta se coracao vermelho
		if ($(this).data('liked') == "no") {
			nrLikes++
			$(this).data('liked', "yes")
		} else {
			// diminui se coração cinza
			nrLikes--
			$(this).data('liked', "no")
		}
		alert($(this).data('liked'))
		$(this).find('span').text(nrLikes)

	})



```

## Eventos (ex. click) 

```js
   $(".post h3").on("click", function(){
      alert("Post clicked!")
    });
```

## Alterar/Obter propriedade de vários elementos clicados

Por exemplo mostra o HTML da DIV clickada

```js
$("div").on('click', function(){
      alert($(this).html()
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

## Adicionar e remover classes


```js
	$("elemento").addClass("postItem")
	$("elemento").removeClass("postItem")
	// toggle remove ou adiciona conforme esteja na lista
	$("elemento").toggleClass("postItem")

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

Plugin [animate](https://animate.style)