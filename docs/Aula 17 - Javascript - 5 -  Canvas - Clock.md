
# Desafio do Relógio


```html
<!DOCTYPE html>
<html>
  <head>
    <title>HTML 5 and CSS 3</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, minimal-ui">
      
  </head>

  <body>
      
      <canvas id="clock" width="500" height="500">
      
      Please upgrade your browser.
      </canvas>
    
      
      <script>
          
          function setTime() {
      
        var canvas = document.getElementById("clock");
        var context = canvas.getContext("2d");
        var clockRadius = canvas.width/2;
        
        context.beginPath();
              
          context.fillStyle = "black";
          context.arc(clockRadius, clockRadius, clockRadius, 0, 2*Math.PI);
          context.fill();
          
          context.fillStyle = "white";
          
          context.beginPath();
          context.arc(clockRadius, clockRadius, 10, 0, 2*Math.PI);
          context.fill();
          
          context.font = clockRadius / 10 + "px arial";
          context.textAlign = "center";
          context.textBaseline = "middle";
          
          for (var i = 1; i <= 12; i++) {
              
              context.fillText(i, clockRadius + clockRadius * 0.9 * Math.sin(i * 2*Math.PI / 12), clockRadius - (clockRadius * 0.9 * Math.cos(i * 2 * Math.PI / 12)));
              
          }
          
          
          var hours = new Date().getHours();
          var minutes = new Date().getMinutes();
          var seconds = new Date().getSeconds();
          
          var fullHours = hours % 12 + minutes / 60 + seconds / 3600;
          
          var hoursAngle = fullHours * 2 * Math.PI / 12;
          var minutesAngle = minutes * 2 * Math.PI / 60;
          var secondsAngle = seconds * 2 * Math.PI / 60;
          
          context.strokeStyle = "white";
          context.moveTo(clockRadius, clockRadius);
          context.lineTo(clockRadius + clockRadius * 0.6 * Math.sin(hoursAngle), clockRadius - (clockRadius * 0.6 * Math.cos(hoursAngle)));
          context.lineWidth = 5;
          context.stroke();    
          
          context.moveTo(clockRadius, clockRadius);
          context.lineTo(clockRadius + clockRadius * 0.8 * Math.sin(minutesAngle), clockRadius - (clockRadius * 0.8 * Math.cos(minutesAngle)));
          context.lineWidth = 3;
          context.stroke(); 
          
          context.moveTo(clockRadius, clockRadius);
          context.lineTo(clockRadius + clockRadius * 0.9 * Math.sin(secondsAngle), clockRadius - (clockRadius * 0.9 * Math.cos(secondsAngle)));
          context.lineWidth = 2;
          context.stroke(); 
      
          }
          
          setInterval(setTime, 1000);
          
      </script>
      
  </body>
    
    
</html>

```

```html

```