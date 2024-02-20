Para alterar o tema default do bootstrap a melhor estratégia é alterar as suas varáveis css disponibilizadas para o efeito.
Para uma alteração mais profunda o melhor será compilar uma versão do bootstrap com alterando as suas variáveis SASS.

## Variáveis css

Ver exemplo do clone da página de login do [[e. Mailchimp Login]].

## Sass

Para criar um tema de cores próprias no bootstrap a melhor estratégia é usar o código fonte do BS e alterar as variáveis pretendidas:

1. Descarregar o código fonte do BS ou instalar via npm
	1. Source files em https://getbootstrap.com/docs/5.2/getting-started/download/
2. Depois de ter o BS no projeto criar uma pasta sass onde vamos criar o nosso ficheiro <code>main.sass</code>. 
```sass
$primary: orange;
$secondary: gray;
// $success:       $green !default;
// $info:          $cyan !default;
// $warning:       $yellow !default;
// $danger:        $red !default;
// $light:         $gray-100 !default;
// $dark:          $gray-900 !default;

// change menu humburger icon
// use https://websemantics.uk/tools/image-to-data-uri-converter/ to convert an image to a data:image
$navbar-light-toggler-icon-bg: url("data:image...");
$navbar-dark-toggler-icon-bg: url("data:image...");

//import bs
@import '../bootstrap-5.2.3/scss/bootstrap.scss';

```

3. Instalar e ativar o plugin do VS Code - Live Sass. Vai permitir efetuar a compilação do `mains.sass` num ficheiro `main.css`.
4. Adicionar o ficheiro <code>main.css</code> ao projeto. Este ficheiro será a versão adaptada do Bootstrap.

5. Para customisar `:hover` dos botões é necessário realizar override das variáveis usados pelo BS para o efeito. . Este código deverá estar no `mais.css`mas depois do import do bootstrap.

```css
// Custom SCSS and CSS (overrides bs)
.btn-outline-primary {   
    --bs-btn-hover-bg: rgb(255, 255, 255);
    --bs-btn-border-color: rgb(225, 225, 225);
    --bs-btn-hover-color: black;
}

.btn-primary {
    --bs-btn-hover-bg: #{tint-color(black, 40%)};
}

.btn-outline-primary:hover {
    // border-width: 2px;
}

```





