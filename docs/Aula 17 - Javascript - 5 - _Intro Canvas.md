# Canvas

Componente html usado para desenhar numa página
Tem das utilizações mais diversas, serve de base aos motores gráficos, sendo muito utilizado em jogos e na construção de gráficos em dashboards

Sistema de coordenadas
![](https://www.javascripttutorial.net/wp-content/uploads/2020/09/JavaScript-Canvas.png)

# Exemplos com o uso de canvas

```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML 5 and CSS 3</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, minimal-ui">
      <style>
          #myCanvas {        
              border: 1px solid grey;
          }
      </style>
  </head>
  <body>  
      <canvas id="myCanvas" width="500" height="400">
      </canvas>
      <script>
      
          var myCanvas = document.getElementById("myCanvas");
          var context = myCanvas.getContext("2d");
          
          context.fillStyle = "blue";
          context.fillRect(150, 100, 200, 200);
          
          context.moveTo(150, 100);
          context.lineTo(350, 300);
          
          context.moveTo(150, 300);
          context.lineTo(350, 100);
          
          context.strokeStyle = "#F42924";
          context.stroke();
          
          context.beginPath();
          // context.arc(x,y,r,sAngle,eAngle,counterclockwise)
          context.arc(100, 100, 50, Math.PI, 2*Math.PI * 3/4);
          context.stroke();   
          
          //context.createLinearGradient(x0,y0,x1,y1);
          var textGradient = context.createLinearGradient(200, 50, 300, 50);
          
          textGradient.addColorStop(0, "red");
          textGradient.addColorStop(1, "yellow");
          
          context.fillStyle = textGradient;
          context.font= "20px Arial";
          context.fillText("My Canvas", 200, 50);
          
          
      </script>
   
  </body>
</html>
```