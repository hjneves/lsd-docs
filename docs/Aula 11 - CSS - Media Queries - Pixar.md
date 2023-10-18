Tem por base o repo ex-pixar para adaptar com media queries
https://github.com/hjneves/ex-pixar

- Colocar css num ficheiro separado.
- Incluir icon para menu hamburger

### index.html
Adicionar um icon, desta vez usando uma tag `<svg>` para o menu humburger logo no inicio do `<header>`
https://fontawesome.com/start

```html
<div class="menuIcon">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Pro 6.2.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2022 Fonticons, Inc. --><path d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg>
</div>
<input type="checkbox"/>--
```


### styles.css
```css

/* Add menu icon and hide it per default */
.menuIcon {
	display: none;
	padding: 6px;
	width: 30px;
}
```


### mobile.css

- Criar o novo ficheiro css e efectuar o link no HTML

```css
@media screen and (max-width: 576px) {

	/* Position hamburger icon and the checkbox */
    .menuIcon, header input {
        display: block;
        position: absolute;
        top: 6px;
        left: 6px;
        width: 30px;
        height: 30px;
        margin: 0;
    }
	/* Make checkbox transparent */
    header input {
        opacity: 0;
    }

	/* On mobile hide menu and search on mobile */
    .menu, .search {
        display: none;
    }

	/* Show menu when user fills the hidden checkbox 
	 by touch the humburger menu */
    header input:checked ~ [target] {
        display: block;
     }

	/* Format the li on mobile **/
    .menu li {
        display: block;
        padding: 30px;
        font-size: 1.6em;
        width: 100%;
        text-align: center;
    }

	/* Format the header flex direction */
    header {
        position: absolute;
        background-color: rgba(255, 255, 255, 0.945);
        flex-direction: column-reverse;
        height: 100vh;
        justify-content: space-around;
        
    }

    .grid {
        flex-wrap: wrap;
    }

	/* One column grid on mobile */
    .grid div {
        flex-basis: 100%;
    }
}

```