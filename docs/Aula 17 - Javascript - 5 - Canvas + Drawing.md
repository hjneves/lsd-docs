
# Exemplos com o uso de canvas

```html

<!doctype html>
<html>
<head>
     <title>CANVAS HTML5</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@100;300&display=swap" rel="stylesheet">

    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

    <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
  />
    <style>

        * {
            margin: 0;
            padding: 0;
        }
        canvas {
            width: 100vw;
            height: 100vh;
            background-color: gray;
        }
    </style>

</head>
<body>
    <canvas class="myCanvas"></canvas>

    <script>
        let canvas = document.querySelector(".myCanvas");
        let ctx = canvas.getContext("2d");
        let coord = {
            x: 0,
            y: 0
        }
     
        document.addEventListener('mousedown', start);
        document.addEventListener('mouseup', stop);
        window.addEventListener('resize', resize);
        
        resize();

        function resize() {
	        // innerWidth returns the interior width of the window in pixels. This includes the width of the vertical scroll bar, if one is present.
            ctx.canvas.width = window.innerWidth;
            ctx.canvas.height = window.innerHeight;
        }

        function reposition(event){
	        // The clientX read-only property of the MouseEvent interface provides the horizontal coordinate within the application's viewport at which the event occurred (as opposed to the coordinate within the page).

			// The offsetX read-only property returns the x-coordinate the mouse cursor, relative to the target element.
            coord.x = event.clientX - canvas.offsetLeft;
            coord.y = event.clientY - canvas.offsetTop;
        }

        function start(){
            document.addEventListener('mousemove', draw);
            reposition(event);
        }
        function stop(){
            document.removeEventListener('mousemove', draw);
        }


        function draw(event){
            ctx.beginPath();
            ctx.lineWidth = 2;
            ctx.strokeStyle= '#ACD3ED';
            
            ctx.moveTo(coord.x, coord.y);
            reposition(event);
            ctx.lineTo(coord.x, coord.y);
            ctx.stroke();
        }
    </script>
</body>
</html>
```