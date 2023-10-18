
Exemplo de adaptação ao layout do por do sol
--------------------------------------------

Do breakpoint mais alto para o mais baixo, para ir reutilizando as adaptações e mudando ainda mais nos ecrãs mais pequenos.

```css
@media screen and (max-width: 768px) {

#wrapper {

flex-direction: column;

}

  

#content, #menu {

width: 100%;

}

  

#menu li {

display: inline-block;

}

  

#menu ul li:hover {

padding-left: 0;

}

  

#products .sectionBody div {

flex-basis: 40%;

}

  
  

}

  

@media screen and (max-width: 480px) {

#products .sectionBody div {

flex-basis: 100%;

}

  

}


```

HTML é exatamente o mesmo