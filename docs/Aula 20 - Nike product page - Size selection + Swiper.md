# Desafio - Indicar seleção de tamanho na página de produto

Usar jquery para ler e manipular os elementos do DOM

## Instalar jquery

Instalar a partir do jquery CDN
```html
<script src="https://code.jquery.com/jquery-3.6.4.slim.min.js" integrity="sha256-a2yjHM4jnF9f54xUQakjZGaqYs/V1CYvWpoqZzC2/Bw=" crossorigin="anonymous"></script>
```

Criar a classe de referencia `sizes`na div dos tamanhos
```html
<div class="row row-cols-3 g-2 py-5 sizes">
```

Javascript de gestão dos clicks nos elementos e utilização da classe `bg-secondary`de bootstrap para destacar
```js
 <script>

      $('.sizes a').click(selectSize);

      function selectSize(e) {
	    // clean 
        $('.sizes a').each(function(){
          $( this ).removeClass('bg-secondary');
        })

        $(this).addClass('bg-secondary');
        
      }

    </script>
```


# Substituir carrousel pelo swiper

- Usar swiper [](https://swiperjs.com/get-started)[https://swiperjs.com/get-started](https://swiperjs.com/get-started) 
- permite inserir diversos tipos de sliders na página
- vamos usar múltiplos slides por vista


## Instalação CSS e JS
  ```html
  <link rel="stylesheet" href="https://unpkg.com/swiper@8/swiper-bundle.min.css" />
```

```html
  <script src="https://unpkg.com/swiper@8/swiper-bundle.min.js"></script>
  ```

## Adaptação HTML, CSS e JS
```html
  <!--------- CAROUSEL ---------->

  <div class="container-fluid mt-5">
    <div class="container d-flex position-relative">
      <h4 class="py-4">Também poderás gostar de</h4>
      <div>
        <button class="carousel-control-prev bg-secondary rounded-circle swiper-button-prev top-0 text-white" type="button"
          data-bs-target="#carouselExampleControls" data-bs-slide="prev">

        </button>
        <button class="carousel-control-next bg-secondary rounded-circle swiper-button-next top-0 text-white" type="button"
          data-bs-target="#carouselExampleControls" data-bs-slide="next">
        </button>
      </div>
    </div>
    <div class="swiper">
      <div class="swiper-wrapper">
        <div class="swiper-slide">
          <img src="./images/1.webp" class="img-fluid" alt="...">
        </div>
        <div class="swiper-slide">
          <img src="./images/2.webp" class="img-fluid" alt="...">
        </div>
        <div class="swiper-slide">
          <img src="./images/3.webp" class="img-fluid" alt="...">
        </div>
        <div class="swiper-slide">
          <img src="./images/1.webp" class="img-fluid" alt="...">
        </div>
        <div class="swiper-slide">
          <img src="./images/2.webp" class="img-fluid" alt="...">
        </div>
        <div class="swiper-slide">
          <img src="./images/3.webp" class="img-fluid" alt="...">
        </div>

      </div>
    </div>
  </div>

```

```js
<script>

    const swiper = new Swiper('.swiper', {
      slidesPerView: 3,
      spaceBetween: 30,
      // Navigation arrows
      navigation: {
        nextEl: '.swiper-button-next',
        prevEl: '.swiper-button-prev',
      },
      pagination: {
        el: ".swiper-pagination",
      },
      //mousewheel: true,
      keyboard: true,
      loop: true,
    });

</script>
  ```
  
  
  ```css
  <style>
     :root {
      --swiper-navigation-size: 20px;
     }
  </style>
   ```
