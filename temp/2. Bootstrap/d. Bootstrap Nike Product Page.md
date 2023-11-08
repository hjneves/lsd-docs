# custom-bootstrap.scss
```scss 

// 1. Include functions first (so you can manipulate colors, SVGs, calc, etc)
@import "../bootstrap-5.2.3/scss/functions";

$primary: rgb(0, 0, 0);
$secondary: rgb(211, 211, 211);
// $success:       $green !default;
$info: rgb(153, 46, 0);
// $warning:       $yellow !default;
// $danger:        $red !default;
// $dark:          $gray-900 !default;

// buttons
$btn-padding-y: 1rem;
$btn-font-size: 1rem;

$btn-border-width: 1px;

$btn-hover-bg-shade-amount:       100%;
$btn-hover-bg-tint-amount:        0%;

// inputs
$input-bg: rgb(241, 241, 241);
$input-btn-focus-box-shadow: transparent;

// accordion
$accordion-button-active-bg: white;
$accordion-button-focus-border-color:   transparent;
$accordion-button-focus-box-shadow:    transparent;
$accordion-body-padding-x: 0;

// Carousel
$carousel-control-width: 90px;

//import bs
@import '../bootstrap-5.2.3/scss/bootstrap.scss';



// Custom SCSS and CSS (overrides bs)
.btn-outline-primary {   
    --bs-btn-hover-bg: rgb(255, 255, 255);
    --bs-btn-border-color: rgb(225, 225, 225);
    --bs-btn-hover-color: black;
}

.btn-primary {
    --bs-btn-hover-bg: #{tint-color(black, 40%)};
}

```


# Styles.css
```css
.jordan {
    width: 24px;
    height: 24px;
}

.fs-7 {
    font-size: 0.75rem;
}

.form-control:hover {
    background-color: rgb(231, 231, 231);
}

.carousel-control-prev, .carousel-control-next {
    width: 60px;
    height: 60px;
}

.carousel-control-prev {
    left: calc(100% - 140px);
}

.footer {
    font-family: "Oswald", sans-serif;
}

```

# First header

```html no-wrap
    <div class="container-fluid bg-light d-flex justify-content-between py-2">
        <div>
          <a href="#">
            <svg class="jordan">
              <path d="M14.4 5.52v-.08q0-.56......."></path>
            </svg>
          </a>
        </div>
        
        <div>
          <a class="fs-7 fw-normal text-decoration-none px-2" href="#">Procurar uma loja</a><span>|</span>
          <a class="fs-7 fw-normal text-decoration-none px-2" href="#">Ajuda</a><span>|</span>
          <a class="fs-7 fw-normal text-decoration-none px-2" href="#">Aderir</a><span>|</span>
          <a class="fs-7 fw-normal text-decoration-none px-2" href="#">Iniciar sessão</a>
        </div>
    </div>
```

# Navbar

```html
<div>
    <div class="container d-flex justify-content-between">
      <div>
        <svg aria-hidden="true" class="pre-logo-svg" focusable="false" viewBox="0 0 24 24" role="img" width="60px" height="60px" fill="none"><path fill="currentColor" fill-rule="evenodd" d="M21 8.719L7.836 14.303C6.74 14.768 5.818 15 5.075 15c-.836 0-1.445-.295-1.819-.884-.485-.76-.273-1.982.559-3.272.494-.754 1.122-1.446 1.734-2.108-.144.234-1.415 2.349-.025 3.345.275.2.666.298 1.147.298.386 0 .829-.063 1.316-.19L21 8.719z" clip-rule="evenodd"></path></svg>
      </div>
      <div>
        <nav class="navbar navbar-expand-lg bg-body-tertiary">
          <div class="container-fluid">

            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
              <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
              <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item">
                  <a class="nav-link" aria-current="page" href="#">Novidades e Destaques</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#">Homem</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#">Mulher</a>
                </li>
                <li class="nav-item">
                  <a class="nav-link" href="#">Criança</a>
                </li>
              </ul>
              <form class="" role="search">
                <div class="input-group position-relative">
                  <button class="btn position-absolute mt-1 op-0 start-0" type="button" id="button-addon1">
                    <i class="bi bi-search"></i>
                  </button>
                  <input type="text" class="my-3 form-control rounded-pill border-0" placeholder="" aria-label="Example text with button addon" aria-describedby="button-addon1">
                  <button class="btn" type="button" id="button-addon1">
                    <i class="bi bi-heart"></i>
                  </button>
                  <button class="btn" type="button" id="button-addon1">
                    <i class="bi bi-bag"></i>
                  </button>
                </div>
              </form>
            </div>
          </div>
        </nav>
      </div>
    </div>
```

# Info box
```html
    <div class="container-fluid bg-light border-bottom">
      <div class="row justify-content-center align-items-center g-2">
        <div class="fs-7 col-6 col-md-2">
          <p class="text-center">Os Members obtêm envio gratuito e devoluções gratuitas no prazo de 30 dias. <a class="link" href="#">Junta-te a nós</a> <a class="link" href="#">Saber mais</a></p>
        </div>
      </div>
    </div>

```


# Grid - fotografias + detalhes
```html

<div class="container mt-lg-5">
      <div class="row">
        <div class="col-md">
          <div class="row row-cols-2 g-3 me-4">
            <div class="col"><img src="./images/1.webp" class="img-fluid " alt=""></div>
            <div class="col"><img src="./images/2.webp" class="img-fluid " alt=""></div>
            <div class="col"><img src="./images/3.webp" class="img-fluid " alt=""></div>
            <div class="col"><img src="./images/4.webp" class="img-fluid " alt=""></div>
            <div class="col"><img src="./images/5.webp" class="img-fluid " alt=""></div>
            <div class="col"><img src="./images/6.webp" class="img-fluid " alt=""></div>
          </div>
        </div>
        <div class="col-6 col-lg-4">
          <p class="text-info mb-1">Acesso para Members</p>
          <h1 class="h1 my-0">Nike Dunk Low</h1>
          <p class="my-0">Sapatilhas para homem</p>
          <p class="mt-4">119,99 €</p>

<!--- Sizes Grid ---->
          <div class="row row-cols-3 g-2 py-5">
            <div class="col ">
              <a name="" id="" class="btn btn-outline-primary rounded-2 w-100" href="#" role="button">EU 38,5</a>
            </div>
            <div class="col">
              <a name="" id="" class="btn btn-outline-primary rounded-2 w-100" href="#" role="button">EU 38,5</a>
            </div>
            <div class="col" disabled>
              <a name="" id="" class="btn btn-secondary bg-light text-secondary border-0 rounded-2 w-100" disabled href="#" role="button">EU 38,5</a>
            </div>
            <div class="col ">
              <a name="" id="" class="btn btn-outline-primary rounded-2 w-100" href="#" role="button">EU 38,5</a>
            </div>
            <div class="col">
              <a name="" id="" class="btn btn-outline-primary rounded-2 w-100" href="#" role="button">EU 38,5</a>
            </div>
            <div class="col" disabled>
              <a name="" id="" class="btn btn-secondary bg-light text-secondary border-0 rounded-2 w-100" disabled href="#" role="button">EU 38,5</a>
            </div>
            <div class="col ">
              <a name="" id="" class="btn btn-outline-primary rounded-2 w-100" href="#" role="button">EU 38,5</a>
            </div>
            <div class="col">
              <a name="" id="" class="btn btn-outline-primary rounded-2 w-100" href="#" role="button">EU 38,5</a>
            </div>
            <div class="col" disabled>
              <a name="" id="" class="btn btn-secondary bg-light text-secondary border-0 rounded-2 w-100" disabled href="#" role="button">EU 38,5</a>
            </div>
          </div>

          <a name="" id="" class="btn btn-primary rounded-pill w-100 my-2" href="#" role="button">Adicionar ao carrinho</a>
          <a name="" id="" class="btn btn-outline-primary rounded-pill w-100" href="#" role="button">Adicionar ao carrinho</a>

          <div class="mt-5">
            <p class="lh-lg">Aperfeiçoa o teu look num estilo retro de basquetebol com as Nike Dunk Low. Criado para o campo, mas adaptado para as ruas, este ícone dos anos 80 regressa com uma parte superior em pele resistente e logótipos Swoosh duplos inspirados em tinta de spray. Com um estilo vintage, a boca almofadada de corte baixo permite-te enfrentar o jogo em qualquer lugar com conforto.
            </p>
            <ul class="px-3">
              <li>Cor apresentada: Branco/Cinzento Cool/Light Iron Ore/Preto</li>
              <li>Estilo: FD0661-100</li>
            </ul>
          </div>

          <div class="my-5">
            <a href="#" >Ver detalhe dos produtos</a>
          </div>

  <!-- Modal -->
        <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
          <div class="modal-dialog modal-dialog-centered modal-lg">
            <div class="modal-content">
              <div class="modal-header border-0 align-items-start">
                <div class="row">
                  <div class="col-2">
                    <img class="img-fluid" src="./images/1.webp" />
                  </div>
                  <div class="col">
                    <p>Nuke Dunk Low</p>
                    <p>€89.99</p>
                  </div>
                </div>
                <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>

              </div>
              <div class="modal-body">
                <p>
                  Whether you're a hooper, skater or just love kicks, the Nike Dunk Low has been a fave for many
                  athletes for decades. Durable leather gives you a classic '80s feel while the rubber sole gives grip
                  and traction. It's time to play.
                </p>

                <p class="fw-semibold">Old-School Style</p>

                <p>Dunks are durable, meaning real and synthetic leather combine to make these shoes last through many
                  days of play.
                </p>

                <p>Heritage Look</p>

                <p>Extra padding on the collar and tongue, plus the low-profile midsole give a classic feel—like the
                  original Dunk.
                </p>

                <p>Made to Play Anywhere</p>

                <p>The full-length rubber sole gives durable traction across different surfaces. Fun fact: the circular
                  tread was originally meant to help basketball players pivot on the court.
                </p>
              </div>
            </div>
          </div>
        </div>

          <!--------- ACCORDION ---------->

          <div class="accordion-item border-start-0 border-end-0">
            <h2 class="accordion-header" id="headingTwo">
              <button class="fs-5 px-0 accordion-button collapsed" type="button" data-bs-toggle="collapse"
                data-bs-target="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">
                <div class=" d-flex justify-content-between w-100">
                  <span>Avaliações (4)</span>
                  <span class="fs-6">
                    <i class="bi bi-star-fill"></i>
                    <i class="bi bi-star-fill"></i>
                    <i class="bi bi-star-fill"></i>
                    <i class="bi bi-star-fill"></i>
                    <i class="bi bi-star-half"></i>

                  </span>
                </div>
              </button>
            </h2>
            <div id="collapseTwo" class="accordion-collapse collapse" aria-labelledby="headingTwo">
              <div class="accordion-body">
                <div class="my-2">
                  <p>
                    <span class="fs-6">
                      <i class="bi bi-star-fill"></i>
                      <i class="bi bi-star-fill"></i>
                      <i class="bi bi-star-fill"></i>
                      <i class="bi bi-star-fill"></i>
                      <i class="bi bi-star-half"></i>

                    </span>
                    <span class="ms-4 ">4,5 Estrelas</span>
                  </p>
                  <p><a href="">Escreve uma avaliação</a></p>
                </div>
                <div class="py-3">
                  <div class="py-2">
                    <p class="fs-6">Good</p>
                    <p>
                      <span class="fs-6">
                        <i class="bi bi-star-fill"></i>
                        <i class="bi bi-star-fill"></i>
                        <i class="bi bi-star-fill"></i>
                        <i class="bi bi-star-fill"></i>
                        <i class="bi bi-star-fill"></i>
                      </span>
                      <span class="ms-4 ">Sipos12345466 - 31/01/2023</span>
                    </p>
                    <p>Quality and performance great, I run 30% faster</p>
                  </div>
                  <div class="py-2">
                    <p class="fs-6">Excellent</p>
                    <p>
                      <span class="fs-6">
                        <i class="bi bi-star-fill"></i>
                        <i class="bi bi-star-fill"></i>
                        <i class="bi bi-star-fill"></i>
                        <i class="bi bi-star-fill"></i>
                        <i class="bi bi-star-half"></i>
                      </span>
                      <span class="ms-4 ">Loris2342345 - 31/01/2023</span>
                    </p>
                    <p>Quality and performance great, I run 30% faster</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
          


        </div>
      </div>
</div>

```

# Carousel

```html
<div class="container-fluid mt-5">
    <div class="container d-flex position-relative">
      <h4 class="py-4">Também poderás gostar de</h4>
    <div>
      <button class="carousel-control-prev bg-secondary rounded-circle" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next bg-secondary rounded-circle" type="button" data-bs-target="#carouselExampleControls" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
    
    </div>
    <div id="carouselExampleControls" class="carousel slide" data-bs-ride="carousel">
      <div class="carousel-inner">
        <div class="carousel-item active">
          <div class="row row-cols-3">
            <div class="col">
              <img src="./images/1.webp" class="img-fluid" alt="...">
            </div>
            <div class="col">
              <img src="./images/2.webp" class="img-fluid" alt="...">
            </div>
            <div class="col">
              <img src="./images/3.webp" class="img-fluid" alt="...">
            </div>
            
          </div>
        </div>
        <div class="carousel-item">
          <div class="row row-cols-3">
            <div class="col">
              <img src="./images/1.webp" class="img-fluid" alt="...">
            </div>
            <div class="col">
              <img src="./images/2.webp" class="img-fluid" alt="...">
            </div>
            <div class="col">
              <img src="./images/3.webp" class="img-fluid" alt="...">
            </div>
            
          </div>
        </div>
      </div>
    
    </div>
  </div>
  ```
  
# Footer

```html
 <!--------  FOOTER  ---------->
  <div class="container-fluid bg-dark py-4">
    <div class="container">
      <div class="row">
        <div class="col footer fs-7">
          <p><a class="link-light text-decoration-none" href="#">CARTÕES DE OFERTA</a></p>
          <p><a class="link-light text-decoration-none" href="#">PROCURAR UMA LOJA</a></p>
          <p><a class="link-light text-decoration-none" href="#">NIKE JOURNAL</a></p>
          <p><a class="link-light text-decoration-none" href="#">TORNA-TE MEMBER</a></p>
          <p><a class="link-light text-decoration-none" href="#">FEEDBACK</a></p>
          <p><a class="link-light text-decoration-none" href="#">CÓDIGOS PROMOCIONAIS</a></p>
        </div>
        <div class="col fs-7">
          <p><a class="link-light text-decoration-none footer" href="#">OBTER AJUDA</a></p>
          <p><a class="text-muted text-decoration-none" href="#">Estado da encomenda</a></p>
        </div>
        <div class="col  fs-7">
          <p><a class="link-light text-decoration-none footer" href="#">SOBRE A NIKE</a></p>
          <p><a class="text-muted text-decoration-none" href="#">Estado da encomenda</a></p>
        </div>
        <div class="col  fs-7">
          <p><a class="link-light text-decoration-none footer" href="#">JUNTA-TE A NÓS</a></p>
          <p><a class="text-muted text-decoration-none" href="#">Estado da encomenda</a></p>
        </div>
        <div class="col-3">
          <div class="text-end">
            <button class="btn btn-secondary rounded-circle p-1 px-2 m-1"><i class="bi bi-twitter"></i></button>
            <button class="btn btn-secondary rounded-circle p-1 px-2 m-1"><i class="bi bi-facebook"></i></button>
            <button class="btn btn-secondary rounded-circle p-1 px-2 m-1"><i class="bi bi-youtube"></i></button>
            <button class="btn btn-secondary rounded-circle p-1 px-2 m-1"><i class="bi bi-instagram"></i></button>
          </div>
        </div>

      </div>
      <div class="d-flex text-muted fs-7 justify-content-end">
        <p class="p-2">Guias</p>
        <p class="p-2">Termos de Utilização</p>
        <p class="p-2">Termos de Venda</p>
        <p class="p-2">Detalhes da Empresa</p>
      </div>
      <div class="d-flex text-light fs-7 justify-content-between">
        <div>
          <i class="bi bi-geo-alt-fill"></i>
          <a href="" class="p-2 link-light text-decoration-none">Portugal</a>
          <span class="p-2 text-muted">Termos de Utilização</span>  
        </div>
        <div>
          <a href="" class="text-muted p-2 text-decoration-none">Termos de Venda</a>
          <a href="" class="text-muted p-2 text-decoration-none">Detalhes da Empresa</a>  
        </div>
      </div>

    </div>
  </div>

```

# Seleção de tamanho na página de produto

Usar jquery para ler e manipular os elementos do DOM

## Instalar jquery

Instalar a partir do jquery CDN
```html
<script src="https://code.jquery.com/jquery-3.6.4.slim.min.js" integrity="sha256-a2yjHM4jnF9f54xUQakjZGaqYs/V1CYvWpoqZzC2/Bw=" crossorigin="anonymous"></script>
```

Criar a classe de referencia `sizes` na div dos tamanhos
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
