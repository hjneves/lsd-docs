## CLOCK background

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8" />
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.3/font/bootstrap-icons.css">
  <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
  />   
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <style type="text/css">

    @keyframes spin {
      100% { transform: rotate(360deg); }
    }

    #cx3 {
      width: 1000px;
      height: 1000px;
      background-color: rgba(184,75,31,.2);
      border-radius: 10%;
      animation: spin 60s linear infinite;
    }

    #cx2 {
      width: 600px;
      height: 600px;
      background-color: rgba(0,201,237,.4);
      border-radius: 10%;
      animation: spin 50s linear reverse infinite;
    }

    #cx1 {
      width: 400px;
      height: 400px;
      background-color: rgba(255,255,255,.6);
      border-radius: 10%;
      animation: spin 80s linear infinite;
    }


    #clock {
      width: 380px;
      height: 110px;
      font-family: Helvetica;
    }

    #date {
      width: 380px;
      height: 60px;
      font-family: Helvetica;
    }

   </style>
</head>
<body class="d-flex align-items-center justify-content-center vh-100">

  <div id="cx3" class="position-absolute"></div>
  <div id="cx2" class="position-absolute"></div>
  <div id="cx1" class="position-absolute"></div>
  
  <div class="position-absolute">
    <div id="date" class="display-5 text-center"></div>
    <div id="clock" class="display-1 fw-bold text-center"></div>
  </div>

  <script src="https://unpkg.com/dayjs@1.8.21/dayjs.min.js"></script>
  <script src="https://unpkg.com/dayjs@1.8.21/locale/pt.js"></script>
   <script type="text/javascript">
      
      dayjs.locale('pt');

      function updateClock() {
        document.getElementById("date").innerHTML = dayjs().format('DD MMMM YYYY');
        document.getElementById("clock").innerHTML = dayjs().format('hh:mm:ss');        
      }

      var clockId = setInterval(updateClock, 1000);

    </script>
</body>
</html>

```