# Acerca

<http://getbootstrap.com/>

Framework para o desenvolvimento de web sites
Abordagem mobile first
Desenvolvida pelo twitter
Talvez das frameworks mais usadas
Permite de uma forma rapida realizar o layout de um site, com componentes e formatações pré-definidas
Deixou de requerer JQuery a partir da versão 5.0 (Vue and React compatible)

# Alguns exemplos

<http://expo.getbootstrap.com/>

# Instalação

Vamos usar a versão 5
<https://getbootstrap.com>

Bootstrap CDN

```html
 <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
```

### Começar pelo Starter Template, copiar e explicar
------------------------------------------------

#### Stylesheet - a colocar antes de todas

```html
 <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
```

#### Javascript plugins

```html
```html
<!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
```


# Layout


#### Grid responsive

Constituida por 12 colunas e por breakpoints que determinam o comportamento da grid: `xs, sm,md,lg,xl,xxl`
A colunas deverão estar dentro de uma div `.row`

Por exemplo a classe <code>.col-sm-4</code> cria um coluna de dimensão 4 espaçamentos que sai de stack a partir do breakpoint `sm`

```html
<div class="container">
  <div class="row">
    <div class="col-sm-4">
      One of three columns
    </div>
    <div class="col-sm-4">
      One of three columns
    </div>
    <div class="col-sm-4">
      One of three columns
    </div>
  </div>
</div>
```

A classe `row-cols` e atribuída ao nível da row e define rapidamente o número de colunas que queremos para um determinado conjunto de cols

```html
<div class=“row row-cols-2”>
   <div class=“col”>
   ... 

```


> [!todo] Desafio
> #### Criar uma grid com 2 colunas 50%, com unstack a partir do breakpoint `md`

```html
 <div class="row">
      <div class="col-md-6">
        Metad21
      </div>
      <div class="col-md-6">
        Metade2
      </div>
    </div>
```

# Componentes

## Navbar

Componente pré contruído que disponibiliza um menu responsive numa página.

Copiar o código de componentes/navbar

- elemento nav - uma div com semântica para o browser saber que é uma secção de navegação
- `fixed-top` fixa a navbar 
- Formatar cores na navbar: A navbar é light por defeito, pode-se adicionar a classe `.navbar-dark`para o modo escuro. Usar as classes utilitárias `bg-*` para outras cores de fundo. 

```html
<nav class="navbar navbar-expand-lg navbar-dark bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Dropdown
          </a>
          <ul class="dropdown-menu">
            <li><a class="dropdown-item" href="#">Action</a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><hr class="dropdown-divider"></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled">Disabled</a>
        </li>
      </ul>
      <form class="d-flex" role="search">
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
        <button class="btn btn-outline-success" type="submit">Search</button>
      </form>
    </div>
  </div>
</nav>
```


> [!todo] Desafio
> #### Colocar uma imagem na navbar-brand

formatar a imagem caso necessário

nav img {

}

```html
nav img {

}

 <a class="navbar-brand" href="#"><img src="https://media.glassdoor.com/sqls/5118/pixar-squarelogo-1401932421212.png"></a>  
```


## Responsive Images

Imagem com comportamento responsive, with 100% e height auto 

```html

<div>
	<img src="..." class="img-fluid" alt="...">
</div>
```

O posicionamento das imagens normalmente é feito em `<div>`que estão numa grid ou com um tamanho controlado.

## Cards

Componente com uma imagem um titulo e um body e um botão de ação.
Neste exemplo o card está colocado numa coluna de grid que se encontra ao centro da página

```html
<div class="row justify-content-center">
	<div class="col-4">
		<div class="card">
			<img src="https://dummyimage.com/200x100/" class="card-img-top" alt="...">
			<div class="card-body">
			  <h5 class="card-title">Card title</h5>
			  <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
			  <a href="#" class="btn btn-primary">Go somewhere</a>
			</div>
		</div>
	</div>
</div>
```

## Off Canvas

Componente semelhante a uma model mas que entra no ecrã pela esquerda, direita, topo ou por baixo. Pode criar uma camada escura por cima da página para dar foco ao conteúdo dos off canvas. Pode ser uma alternativa ao menu humburger.
Por defeito o placement é à esquerda, mas podemos alterar, por ex. para a diereita com a classe `offcanvas-end 

```html
<a class="btn btn-primary" data-bs-toggle="offcanvas" href="#offcanvasExample" role="button" aria-controls="offcanvasExample">
  Link with href
</a>
<button class="btn btn-primary" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasExample" aria-controls="offcanvasExample">
  Button with data-bs-target
</button>

<div class="offcanvas offcanvas-start" tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel">
  <div class="offcanvas-header">
    <h5 class="offcanvas-title" id="offcanvasExampleLabel">Offcanvas</h5>
    <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"></button>
  </div>
  <div class="offcanvas-body">
    <div>
      Some text as placeholder. In real life you can have the elements you have chosen. Like, text, images, lists, etc.
    </div>
    <div class="dropdown mt-3">
      <button class="btn btn-secondary dropdown-toggle" type="button" data-bs-toggle="dropdown">
        Dropdown button
      </button>
      <ul class="dropdown-menu">
        <li><a class="dropdown-item" href="#">Action</a></li>
        <li><a class="dropdown-item" href="#">Another action</a></li>
        <li><a class="dropdown-item" href="#">Something else here</a></li>
      </ul>
    </div>
  </div>
</div>
```



## Forms & Tables

Forms encontram-se pré-formatados. Exemplo de um form para login

```html
<form>
  <div class="mb-3">
    <label for="exampleInputEmail1" class="form-label">Email address</label>
    <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
    <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
  </div>
  <div class="mb-3">
    <label for="exampleInputPassword1" class="form-label">Password</label>
    <input type="password" class="form-control" id="exampleInputPassword1">
  </div>
  <div class="mb-3 form-check">
    <input type="checkbox" class="form-check-input" id="exampleCheck1">
    <label class="form-check-label" for="exampleCheck1">Check me out</label>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
```

## Utilities

À semelhança do Tailwind o Bootstrap 5  também tem um conjunto de classes utilitárias para formatar o html

Por exemplo **Margin e Padding**

The classes are named using the format `{property}{sides}-{size}` for `xs` and `{property}{sides}-{breakpoint}-{size}` for `sm`, `md`, `lg`, `xl`, and `xxl`.

Where _property_ is one of:

-   `m` - for classes that set `margin`
-   `p` - for classes that set `padding`

Where _sides_ is one of:

-   `t` - for classes that set `margin-top` or `padding-top`
-   `b` - for classes that set `margin-bottom` or `padding-bottom`
-   `s` - (start) for classes that set `margin-left` or `padding-left` in LTR, `margin-right` or `padding-right` in RTL
-   `e` - (end) for classes that set `margin-right` or `padding-right` in LTR, `margin-left` or `padding-left` in RTL
-   `x` - for classes that set both `*-left` and `*-right`
-   `y` - for classes that set both `*-top` and `*-bottom`
-   blank - for classes that set a `margin` or `padding` on all 4 sides of the element

Where _size_ is one of:

-   `0` - for classes that eliminate the `margin` or `padding` by setting it to `0`
-   `1` - (by default) for classes that set the `margin` or `padding` to `$spacer * .25`
-   `2` - (by default) for classes that set the `margin` or `padding` to `$spacer * .5`
-   `3` - (by default) for classes that set the `margin` or `padding` to `$spacer`
-   `4` - (by default) for classes that set the `margin` or `padding` to `$spacer * 1.5`
-   `5` - (by default) for classes that set the `margin` or `padding` to `$spacer * 3`
-   `auto` - for classes that set the `margin` to auto

```html
<div class="mx-2">

</div>
```




Para colocar a navbar sticky
----------------------------

```html
sticky-top // adicionar esta classe à <nav>
```

DESAFIO
=======

Transformar o site da pixar em Bootstrap

1º reproduzir a estrutura com componentes

2º Customizar com CSS