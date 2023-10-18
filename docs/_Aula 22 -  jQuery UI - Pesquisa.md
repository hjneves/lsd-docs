DESAFIO PESQUISA
----------------

Criar um header section para pesquisa

1º slider range min e maz para preço

2º date picker de … aaa.

3º auto complete, com categorias

```js
<!doctype html>
<html>
<head>
    <title>My Search Page</title>

    <meta charset="utf-8" />
    <meta http-equiv="Content-type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />

    <link rel="stylesheet" href="css/jquery-ui.min.css">
    <style type="text/css">

    h2, body {
      font-family: Helvetica;
    }

    #wrapper, #resultsSection {
      width: 80%;
      padding: 10px;
      margin: 0 auto;
      border: 1px gray solid;
    }
 
    #search, #btnSearch {
      font-size: 1.2em;
      height: 30px;
    }
   
    </style>

</head>
<body>
  
  <div id="wrapper">
   
    <h2>Pesquisa:</h2>
    <input id="search" />
    <button id="btnSearch" type="button">Pesquisar</button>

    <div id="advancedSearch">
      <h3>Advanced</h3> 
      <div>
        <p>
          <label for="amount">Price range:</label>
          <input type="text" id="amount" readonly />  
        </p>
        
        <div id="slider-range"></div>

        <p> From: <input type="text" id="fromDate" /> to: <input type="text" id="toDate" /></p>
      </div>   
    </div>

  </div>
  <div id="resultsSection">
    <p id="searchConditions"></p>
  </div>


  <script type="text/javascript" src="http://code.jquery.com/jquery-latest.min.js"></script>
  <script src="scripts/jquery-ui.min.js"></script>
  <script type="text/javascript">

  $("#btnSearch").click(function(){

    $("#searchConditions").text( "Pesquisar por " + 
      $("#search").val() + " com preços entre " + 
      $( "#slider-range" ).slider( "values", 0 ) + "€ e " + $( "#slider-range" ).slider( "values", 1 ) + "€ e entre a data " + $("#fromDate").datepicker("getDate") + " e " + $("#toDate").datepicker("getDate")
 

      )
  });

   
    $("#advancedSearch").accordion({
      collapsible:true,
      active:false
    });

    $("ul").sortable();



        var availableTags = [
      "ActionScript",
      "AppleScript",
      "Asp",
      "BASIC",
      "C",
      "C++",
      "Clojure",
      "COBOL",
      "ColdFusion",
      "Erlang",
      "Fortran",
      "Groovy",
      "Haskell",
      "Java",
      "JavaScript",
      "Lisp",
      "Perl",
      "PHP",
      "Python",
      "Ruby",
      "Scala",
      "Scheme"
    ];
    $( "#search" ).autocomplete({
      source: availableTags
    });

    // ------------------  Range slider
     $( "#slider-range" ).slider({
      range: true,
      min: 0,
      max: 500,
      values: [ 75, 300 ],
      slide: function( event, ui ) {
        $( "#amount" ).val( ui.values[ 0 ] + "€ - " + ui.values[ 1 ] + "€" );
      }
    });
    $( "#amount" ).val( $( "#slider-range" ).slider( "values", 0 ) +
      "€ - " + $( "#slider-range" ).slider( "values", 1 ) + "€" );


    // ------------------- date range picker
    $("#fromDate").datepicker({
      dateFormat: "yy-mm-dd",
      onClose: function(selectedDate){
        $("#toDate").datepicker("option","minDate",selectedDate);
      }
    });
    $("#toDate").datepicker({
      dateFormat: "yy-mm-dd",
      onClose: function(selectedDate){
        $("#fromDate").datepicker("option","maxDate",selectedDate);
      }
    });

  </script>

</body>
</html>
```

