What is Responsive Web Design?
------------------------------

Responsive web design makes your web page look good on all devices.

Responsive web design uses only HTML and CSS.

Responsive web design is not a program or a JavaScript.

---

Designing For The Best Experience For All Users
-----------------------------------------------

Web pages can be viewed using many different devices: desktops, tablets, and phones. Your web page should look good, and be easy to use, regardless of the device.

Web pages should not leave out information to fit smaller devices, but rather adapt its content to fit any device:

![](77BE1B6391A32BCFB981B558855B3D46.png) 
Desktop 

![](F4392B1D1AA8DFFE147A813890C5BC8F.png) 
Tablet 

![](6123D0A656B5738BC2043A370575AA2F.png) 
Phone 

It is called responsive web design when you use CSS and HTML to resize, hide, shrink, enlarge, or move the content to make it look good on any screen.

CSS Syntax
----------

@media not|only *mediatype *and* (media feature)* {*
 CSS-Code;
*}

Media queries for a mobile based CSS
------------------------------------

```css


@media screen and (min-width: 480px) {
    body {
        background-color: lightgreen;
    }
}
```

Media queries for a desktop based CSS
-------------------------------------

```css


@media screen and (max-width: 768px) {
    body {
        background-color: lightgreen;
    }
}
```

Exemplos de responsive
----------------------

Em regra queremos adapatar fundamentalmente 2 estruturas

- menu

- grelha da página

- outros elementos dimensão %

```html
<!doctype html>
<html>
<head>
    <title>Responsive Site</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@100;300&display=swap" rel="stylesheet">

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

    <link rel="stylesheet" type="text/css" href="./css/styles.css">
    <link rel="stylesheet" type="text/css" href="./css/mobile.css">

    <style type="text/css">
    </style>

</head>

<body>
    <div id="wrapper">
        <div id="menu">
            <input type="checkbox" name="">
            <p><i class="fa fa-align-left"></i></p>
            <ul>
                <li>About</li>
                <li>Portfolio</li>
                <li>Experiences</li>
                <li>Hello</li>
            </ul>
        </div>



        <div class="grid">
            <div>A</div>
            <div>B</div>
            <div>C</div>
            <div>D</div>
        </div>

    </div>
   

</body>
</html>
```

CSS (style.css)
---------------

```css
body {
    background-color: tomato;
    margin: 0;
}

#wrapper {
    position: relative;
    max-width: 768px;
    background-color: white;
    margin: 0 auto;
    height: 100vh;
}

#menu ul {
    list-style: none;
    margin: 0;
    padding: 0;
}

#menu li {
    display: inline-block;
    padding: 4px;
}

#menu p, #menu input {
    display: none;
}


#menu p {
    margin: 0;
    padding: 4px;
    font-size: 1.5em;
}

#menu input {
    position: absolute;
    width: 40px;
    height: 40px;
    left:0; top:0;
    opacity: 0;
}

#menu input:checked ~ ul {
    display: block;
}

.grid {
    display: flex;
    gap: 4px;
    flex-wrap: wrap;
}

.grid div {
    flex-basis: 20%;
    flex-grow: 1;
    height: 160px;
    background-color: lightblue;
}
```

CSS (mobile.css)
----------------

```css
@media screen and (max-width: 768px)  {
	body {
		background-color: lightgray;
	}

	#wrapper {
		margin: 0 8px;
	}

	.grid div{
		flex-basis: 40%;
	}
}


@media screen and (max-width: 480px) {

	body {
		background-color: black;
	}

	#menu p {
		display: block;
	}
	#menu input {
		display: block;
	}

	#menu ul {
		display: none;
	}
	#menu li {
		display: block;
	}

	#menu {
		position: absolute;
		top:0;
		left:0;
		background-color: rgba(255,255,255,0.8);
		width: 100%;
	}
	
	#menu ul {
		height: 100vh;
		list-style: none;
		font-size: 2.6em;
		line-height: 2.2em;
	}

	.grid div{
		flex-basis: 100%;
	}
}
```