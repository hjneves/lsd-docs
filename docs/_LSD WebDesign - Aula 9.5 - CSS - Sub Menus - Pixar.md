Sub Menus no layout da PIXAR
----------------------------

CSS
---

```css
       #menuItems {
      font-family: Helvetica;
      color: gray;
    }

    .selected {
      border: 1px solid gray;
    }

    #menuItems ul a {
      text-decoration: none;
      color: gray;
    }

    #menuItems ul li {
      float: left;
      chrome
      position: relative;
      padding: 10px;
      margin-right: 0;
    }
    /* Quebra float nos ultimos li p */
    #menuItems ul ul li {
      float: none;
    }

    /* Define hover para todos os li que tem um ul por cima 
    div p - Selects all <p> elements inside <div> elements  1
    div > p - Selects all <p> elements where the parent is a <div> element
    */
    #menuItems ul li:hover {
      background-color:#f6f6f6
    }

    /* Define o submenu container 
    posição absolute para posicionar face ao seu pai relative
    */
    #menuItems ul ul { 
      display: none;
      /*Position relative criar espaço para entre li apresentar caixa com o ul de 2º nível*/
      position: absolute;
      padding: 0;  /*   Elimina o espaço a esquerda*/
      background-color: white;
      width: 200px;
      top:100%;
      left:0;
    }

    #menuItems ul li:hover > ul {
      display: block;
    }
```

HTML
----

```html
     <!-- Secção de menu    -->
   <div id="menu">
      <!-- Menu Items -->
      <div id="menuItems">
        <ul>
          <li class="selected"><a href="index.html">About</a></li>
          <li><a href="services.html">Services</a>
            <ul>
              <li>WebDesign</li>
              <li>Game Development</li>
              <li>Consulting</li>
            </ul>
          </li>
          <li><a href="products.html">Products</a>
            <ul>
              <li>Templates</li>
              <li>Fonts</li>
              <li>Backgrounds</li>
            </ul>
          </li>
          <li><a href="support.html">Support</a></li>
          <li><a href="contacts.html">Contacts</a></li>
        </ul>

      </div>
      <!-- Pesquisa no menu -->
      <div id="menuSearch">
        <input type="text" name="searchBox" placeholder="pesquisa..."/>
        
      </div>


   </div>

```

Media queries