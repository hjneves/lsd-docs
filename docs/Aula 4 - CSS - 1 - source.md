A `<meta>` viewport element gives the browser instructions on how to control the page's dimensions and scaling.

The `width=device-width` part sets the width of the page to follow the screen-width of the device (which will vary depending on the device).

The `initial-scale=1.0` part sets the initial zoom level when the page is first loaded by the browser.

**CSS1.html**
-------------

```html
<!doctype html>
<html>
<head>
    <title>My first CSS file</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <style type="text/css">
        
        body {
            background-color: lightgray;
            font-size: 100%;
            font-family: Helvetica;
            margin: 0;
        }

        p {
            color: gray;
            font-size: 1.2em;
            text-align: center;
            padding:0; margin: 0;
        }

        div {
            height: 300px;
            padding: 8px;
            background-color: white;
            overflow: hidden;
        }

        .heading {
            background-color: yellow;
            height: 400px;
            padding: 0;
        }

        #menu {
            background-color: lightgreen;
        }

        span {
            color: red;
        }

        img {
            width: 100%;
        }

        .tag {
            display: inline; /*none - esconde o elemento*/
            border: 2px black solid;
            margin: 4px;
            padding: 2px;
        }

        .leftContainer {
            float: left;
            width: 75%;
            background-color: lightyellow;
            padding: 0;
        }

        .rightContainer {
            float: right;
            width: 25%;
            background-color: lightblue;
            padding: 0;
        }

        .centerContainer {
            width: 50%;
/*            margin-left: auto;
            margin-right: auto;
*/
            margin: 0 auto;
        }


    </style>

</head>
<body>

    <nav id="menu">
        <p>About | Products | Services | Contacts</p>
    </nav>

    <div class="heading">
        <img src="images/bird.jpg">
    </div>

    <div>
    <p class="tag"><a href="">pássaros</a></p>
    <p class="tag">amarelos</p>
    <p class="tag">bico curto</p>
    </div>

    <div>
        <p>
            Donec fringilla eros nec velit imperdiet, in scelerisque magna facilisis. Etiam vitae placerat nisi, vel efficitur nisl. Duis sit amet congue est. Sed eu lorem tincidunt, sagittis felis dapibus, ultrices nulla. Nam vitae dapibus nibh. Donec egestas dolor turpis. Nam euismod ut orci sed porttitor. Etiam bibendum nunc a molestie ornare. Etiam pellentesque quam felis, vitae pharetra quam faucibus ullamcorper. Mauris gravida blandit ultrices. Cras tempus tristique odio ut sodales. Morbi fermentum tempus nibh. Sed eget ornare felis. In congue tincidunt mauris. <span>Nunc aliquet ultricies dolor et pulvinar</span>.
        </p>
        <p>
            Donec fringilla eros nec velit imperdiet, in scelerisque magna facilisis. Etiam vitae placerat nisi, vel efficitur nisl. Duis sit amet congue est. Sed eu lorem tincidunt, sagittis felis dapibus, ultrices nulla. Nam vitae dapibus nibh. Donec egestas dolor turpis.
        </p>
    </div>
    <div class="leftContainer">
        <p>Coluna da esquerda</p>
    </div>
    <div class="rightContainer">
        <p>Coluna da direita</p>
    </div>

    <div class="centerContainer">
        <p>Centrado</p>
    </div>


   
</body>
</html>
```