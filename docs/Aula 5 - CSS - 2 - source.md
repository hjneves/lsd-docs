CSS2.html
---------

```html
<!doctype html>
<html>
<head>
    <title>My second CSS file</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@100;300&display=swap" rel="stylesheet">
    <style type="text/css">
        
        @font-face {
            font-family: "OswaldRegular";
            src: url("fonts/Oswald-Regular.ttf");
        }
        @font-face {
            font-family: "OswaldLight";
            src: url("fonts/Oswald-Light.ttf");
        }

        body {
            background-color: lightgray;
            font-size: 100%;
            font-family: 'OswaldRegular', sans-serif;
            margin: 0;
        }

        div {
            font-family: "OswaldLight", sans-serif;
        }

        p {
            font-family: "OswaldRegular";
        }

        #menu {
            position: sticky;
            top: 0px;
            background-color: lightyellow;
        }


        #menu p {
            display: inline-block;
            font-family: Helvetica;
            color: green;
            width: 100px;
            height: 100px;
            border: 1px solid green;
            border-radius: 50px;
            text-align: center;
            line-height: 100px;
        }

        #menu p:hover{
            background-color: green;
            color: white;
        }

        #wrapper {
            position: relative;
            max-width: 768px;
            margin: 0 auto;
            background-color: lightyellow;
        }

        .box {
            position: relative;
            height: 100px;
        }

        .box1 {
            background-color: black;
            left: 25%;
            width: 75%;
        }
        .box2 {
            background-color: orange;
            left: 50%;
            width: 50%;
        }
        .box3 {
            background-color: blue;
            left: 75%;
            width: 25%;
        }

        .highlight {
            position: absolute;
            top: 100px;
            left: 300px;
            font-size: 3em;
        }

        .highlight:hover {
            color: white;
            background-color: black;
        }

        .article {
            color: darkgreen;
        }

        p.article {
            margin-left: 10px;
        }

        h2.article {
            margin-left: 20px;
        }


        a:visited {
            color: green;
            text-decoration: none;
        }

        a:link {
            color: green;
            text-decoration: none;
        }

        .boxGrid {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            grid-template-rows: 100px;
            grid-gap: 1px;
        }

        .boxGrid div {
            background-color: tomato;
            padding: 4px;
        }

        .boxFloat div {
            float: left;
            width: calc(100% / 3);
            height: 100px;
            background-color: olive;
            border: 1px solid white;
            box-sizing: border-box;
        }

        .clear {
            clear: both;
        }

    </style>

</head>
<body>

    <div id="wrapper">

        <div>
            <div class="box box1"></div>
            <div class="box box2"></div>
            <div class="box box3"></div>
        </div>
        <div class="highlight">
            <p>STAIRS</p>
        </div>

        <nav id="menu">
            <p>About</p>
            <p>Products</p>
            <p>Services</p>
            <p><a href="contacts.html">Contacts</a></p>
        </nav>


        <div>
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse luctus, orci aliquam ultrices ullamcorper, ipsum arcu maximus metus, sit amet tristique erat libero eu metus. Donec aliquam vel tortor pellentesque rhoncus. In interdum tellus a lobortis commodo. Maecenas rutrum in est non tincidunt. Cras commodo mattis justo, sit amet placerat lorem bibendum non. Nulla ut ultricies enim. Mauris vehicula nulla id velit placerat, quis fringilla neque lacinia. Maecenas scelerisque ut velit vel mollis. Nullam nisl est, cursus id enim sed, egestas dignissim nulla. Aenean non ipsum a felis maximus tristique. Nulla vel gravida turpis, et auctor neque. Etiam ac mi elit. Quisque rhoncus elit nunc, ac volutpat velit malesuada eget. Cras euismod libero justo, eu semper leo sollicitudin a. Duis sit amet feugiat quam.

        </div>
        <div>
            Praesent nec lobortis ipsum. Donec sed est odio. Fusce eu euismod eros. Donec tempus, enim id placerat varius, ligula mi condimentum nisi, in eleifend elit ex eu arcu. Donec sem dolor, malesuada eu ornare id, efficitur at risus. Curabitur nec convallis tortor. Morbi tincidunt mauris in ex auctor luctus. Morbi est nunc, sagittis ac sodales ac, lacinia eget erat.

            Aliquam sed nisl lobortis, commodo metus eu, sollicitudin dui. Donec sed nibh libero. Morbi consequat sapien ac ultrices faucibus. Aenean ligula lacus, dictum nec eleifend at, cursus sit amet odio. Fusce eleifend vehicula rhoncus. Morbi ultrices risus urna, vel consectetur lectus mollis vel. Nunc sit amet ipsum sodales, consectetur elit vitae, tincidunt lectus. Suspendisse quam eros, dapibus at condimentum et, maximus ac odio. Nunc tempus molestie tempor. Nam lobortis risus porta orci consectetur aliquet. Sed nisl urna, faucibus ut imperdiet sit amet, consectetur eget diam.

        </div>
        <div>
            <h2 class="article">Article title</h2>
            <p class="article">
                Praesent nec lobortis ipsum. Donec sed est odio. Fusce eu euismod eros. Donec tempus, enim id placerat varius, ligula mi condimentum nisi, in eleifend elit ex eu arcu. Donec sem dolor, malesuada eu ornare id, efficitur at risus. Curabitur nec convallis tortor. Morbi tincidunt mauris in ex auctor luctus. Morbi est nunc, sagittis ac sodales ac, lacinia eget erat.

                Aliquam sed nisl lobortis, commodo metus eu, sollicitudin dui. Donec sed nibh libero. Morbi consequat sapien ac ultrices faucibus. Aenean ligula lacus, dictum nec eleifend at, cursus sit amet odio. Fusce eleifend vehicula rhoncus. Morbi ultrices risus urna, vel consectetur lectus mollis vel. Nunc sit amet ipsum sodales, consectetur elit vitae, tincidunt lectus. Suspendisse quam eros, dapibus at condimentum et, maximus ac odio. Nunc tempus molestie tempor. Nam lobortis risus porta orci consectetur aliquet. Sed nisl urna, faucibus ut imperdiet sit amet, consectetur eget diam.


            </p>
        </div>

        <h2>Grid layout</h2>
        <div class="boxGrid">
            <div>Cell1</div>
            <div>Cell2</div>
            <div>Cell3</div>
        </div>

        <h2>Float layout</h2>
        <div class="boxFloat">
            <div>Cell1</div>
            <div>Cell2</div>
            <div>Cell3</div>
        </div>
        <div class="clear"></div>


    </div>
   
   
</body>
</html>
```