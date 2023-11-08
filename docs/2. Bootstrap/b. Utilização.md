
O bootstrap é uma framework de desenvolvimento web que disponibiliza componentes pre-formatados, um sistema de layout para estruturar o UI, helpers e utilitários para as principais propriedades css.

A utilização do bootstrap pode ser apenas parcial, por ex. para realizar o layout dos ecrãs e todo o css de formatação dos elementos ser depois desenhado com css próprio.  

O [starter template](https://getbootstrap.com/docs/5.3/getting-started/introduction/) é uma página básica que exemplifica a estrutura de um ficheiro html com bootstrap. 

```html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Bootstrap demo</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
  </head>
  <body>
    <h1>Hello, world!</h1>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-C6RzsynM9kWDrMNeT87bh95OGNyZPhcTNXj1NW7RuBCsyN/o0jlpcV8Qyq46cDfL" crossorigin="anonymous"></script>
  </body>
</html>
```

O link para o nosso ficheiro css, ex. styles.css, deverá vir depois do link para o ficheiro css do Bootstrap. Desta forma garantimos que as nossas regras vão-se sobrepor às regras do bootstrap.

Por exemplo,
```html
 <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-T3c6CoIi6uLrA9TneNEoa7RxnatzjcDSCmG1MXxSR1GAsXEV/Dwwykc2MPK8M2HN" crossorigin="anonymous">
    <link href="./css/styles.css" rel="stylesheet" />
```

# Layout

## Grid responsive

A grelha de layout é constituída por 12 colunas e por breakpoints, relacionados com a dimensão do viewport, que determinam o comportamento da grid: `xs, sm, md, lg, xl, xxl`

A grelha é constituída por uma ou mais linhas, que por sua vez têm colunas. Nma grelha bem estruturada as colunas `.col` deverão estar dentro de uma div `.row`

Por exemplo a classe `.col-sm-4` cria um coluna de dimensão "4 espaçamentos em 12" que sai de stack a partir do breakpoint `sm`. Recordar que o bootstrap é mobile based, ou seja, no casa da grelha ela começa sempre as colunas stacked e o breakpoint indica a partir de que dimensão as colunas passa a ficar unstacked, ou seja, lado a lado.

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

A classe `row-cols` e atribuída ao nível da row e define rapidamente o número de colunas que queremos para um determinado conjunto de cols. Útil numa situação em que queremos apresentar um conjunto de caias em duas colunas,

```html
<div class=“row row-cols-2”>
   <div class=“col”>Coluna 1</div>
   <div class=“col”>Coluna 1</div>
   ... 
   <div class=“col”>Coluna 1</div>
</div>
```


> [!todo] Nota
> Se não indicarmos nenhuma dimensão na class de `.col` a grelha vai ser dividida de igual forma por todas as colunas

Neste caso como a linha tem duas colunas, e nenhuma delas tem um valor de dimensão, cada uma delas vai receber uma tamanho de 6.
```html
 <div class="row">
      <div class="col-md">
        Metade1
      </div>
      <div class="col-md">
        Metade2
      </div>
    </div>
```

# Componentes

## Navbar

Navbar é um componente pré-definido que disponibiliza um header com um logo e um menu responsive numa página. O elemento html wrapper `<nav>`  indica ao browser que é uma secção de navegação.

Algumas notas sobre a navbar:
- Ela é fluida por defeito (ocupa 100% do espaço), mas pode ser colocada noutro elemento container
- Para se obter um posicionamento fixo deve-se usar  a classe `fixed-top` na nav. 
- A navbar é light por defeito. Pode-se adicionar o atributo `data-bs-theme="dark"` para o modo escuro, mas também usar as classes utilitárias `bg-*` para outras cores de fundo. 

```html
<nav class="navbar navbar-expand-lg bg-body-tertiary">
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
          <a class="nav-link disabled" aria-disabled="true">Disabled</a>
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

Para colocar um logo na navbar podemos utilizar o link com a classe `.navbar-brand`para inserir uma determinada imagem e depois formatá-la em css

```html
<a class="navbar-brand" href="#">
	<img src="https://media.glassdoor.com/sqls/5118/pixar-squarelogo-1401932421212.png">
</a>  
```
```css
.navbar-brand img {
	width: 80px;
}
```

## Off Canvas

Este componente é semelhante a uma *modal* mas que entra no ecrã pela esquerda, direita, topo ou por baixo. Pode criar uma camada escura por cima da página para dar foco ao conteúdo do off canvas e pode ser usada como uma alternativa ao menu hamburger.
Por defeito fica colocada à esquerda, mas podemos alterar, por ex. para a direita com a classe `offcanvas-end 

```html

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
  </div>
  
</div>
```

## Imagens responsive

Uma imagem fica responsive se a sua largura for definida relativamente à do seu container. Em bootstrap temos uma classe `.img-fluid` que coloca as imagens com width a 100% e height auto.

```html
<div>
	<img src="..." class="img-fluid" alt="...">
</div>
```

Uma largura de 100% significa que ela vai ocupar toda a largura do seu container `<div>` que poderá estar numa grid ou ter um tamanho pré-definido.

## Cards

Os cartões são componentes que normalmente têm uma estrutura que inclui uma imagem um titulo, um *body* e um botão de ação.

Neste exemplo temos um cartão que está colocado numa coluna que se encontra ao centro da página
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

## Forms

O componente forms disponibiliza todas as principais tags de input pré-formatados. Inclui também um processo de validação de campo obrigatório. 

Exemplo de um form para login, centrado com recurso à flexbox.
```html
<div class="d-flex justify-content-center">
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
</div>
```

## Utilities

À semelhança do Tailwind o Bootstrap 5 também tem um conjunto de classes utilitárias para formatar o html.

Por exemplo a **margin** e o **padding**.

A sintaxe das classes tem por base a seguinte estrutura:
**{property}{sides}-{size}**** sem breakpoint.
**`{property}{sides}-{breakpoint}-{size}`** para os berakpoints `sm`, `md`, `lg`, `xl` e `xxl`.

Onde _property_ pode ser:

-   `m` - para definir `margin`
-   `p` - para definir `padding`

Onde _sides_ pode ser:

-   `t` - para definir `margin-top` ou `padding-top`
-   `b` - para definir `margin-bottom` ou `padding-bottom`
-   `s` - (start) para definir `margin-left` ou `padding-left` em LTR, `margin-right` ou `padding-right` em RTL
-   `e` - (end) para definir `margin-right` ou `padding-right` em LTR, `margin-left` ou `padding-left` em RTL
-   `x` - para definir padding ou margin à esquerda e à direita, `*-left` e `*-right`
-   `y` - para definir padding ou margin em cima e em baixo, `*-top` and `*-bottom`
-   blank - para definir `margin` or `padding` nos 4 lados do elemento.

Para o _size_ temos um valor de `0..5`e `auto`.
O valor `0` coloca uma margin ou padding a 0, o valor de `1` a `5` é de` $spacer\ * 0.25` a `$spacer\ * 3`. 

Alguns exemplos
```html
<!-- Aplica padding top a 0 -->
<div class="pt-0">
</div>

<!-- Aplica padding top e bottom com tamanho 2 a partir do breakpoint medium -->
<div class="py-md-2">
</div>

<!-- Coloca margin de tamanho 2 tanto à esquerda como à direita -->
<div class="mx-2">
</div>
```


Ver mais [utilities](https://getbootstrap.com/docs/5.3/utilities).