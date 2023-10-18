Sub Menus no layout 2 - por do sol
----------------------------------

CSS
---

```css
#menuItems {
  width: 20%;
  margin-top: 100px;
  /*background-color: yellow;*/
  float:left;
}

a {
  color: white;
  font-family: Lato;
  font-size: 1.2em;
  line-height: 180%;
  text-decoration: none;
}

    #menuItems ul {
      list-style: none;

    }
    
    #menuItems ul li {
      /*float: left;*/
      padding-left: 0;
      position: relative;

    }

    #menuItems ul li:hover {
      padding-left: 5px;
      color: #FFF7E5;
    }

    #menuItems ul ul {

      display: none;
      position: absolute;
      top: 0;
      left: 100%;
      padding: 0;
      width: 200px;
    }

    #menuItems ul ul li {
      float: none;
    }

    #menuItems ul li:hover > ul {

      display: block;
    }


```

HTML
----

```html
  <div id="menuItems">
    <ul>
      <li class="menuItem"><a href="#about">About</a></li>
      <li class="menuItem"><a href="#products">Products</a>

        <ul>
          <li><a href="#">Templates</a></li>
          <li><a href="#">Fonts</a></li>
          <li><a href="#">Backgrounds</a></li>
        </ul>

      </li>
      <li class="menuItem"><a href="#services">Services</a>

        <ul>
          <li><a href="#">WebDesign</a></li>
          <li><a href="#">Game Development</a></li>
          <li><a href="#">Consulting</a></li>
        </ul>

      </li>
      <li class="menuItem"><a href="">Support</a></li>
      <li class="menuItem"><a href="">Contacts</a></li>
    </ul>
  </div>
```

Media queries