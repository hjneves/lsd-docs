O que é?
========

Query UI is a widget and interaction library built on top of the jQuery JavaScript Library that you can use to build highly interactive web applications. This guide is designed to get you up to speed on how jQuery UI works. Follow along below to get started.

INSTALAÇÂO
----------

```html

<link rel="stylesheet" href="jquery-ui.min.css">



 <script src="scripts/jquery-ui.min.js"></script>
```

ORGANIZAÇÃO
-----------

- Criar directorias para javascript e css

DRAG, RESIZE, DROP OUT
----------------------

Usar 2 quadrados e 2 circulos

//criar div's e formatá-la

```js
<div class="squareBox"></div>
<div class="squareBox"></div>

<div class="roundBox"></div>
<div class="roundBox"></div>

<script>

    $(".squareBox").draggable()  // permite arrastar o div

    $(".squareBox").resizable()  // permite redimensionar o div (usada por vezes nas caixas de texto das mensagens

    // Permite que a roundBox detect o drop de elementos nela
     $(".roundBox").droppable({
      drop: function(ui, event) {
        alert("Dropped");
        
</script>
```

ACORDION 
---------

```html

   <h2> FAQS: </h2>
    <div id="accordion">

      <h3>Como encomendar</h3>
      <div>
          <p>Plenty of long text description ......</p>
      </div>

      <h3>Não encontro um produto</h3>
      <div>
          <p>Plenty of long text description ......</p>
      </div>

      <h3>Formas de pagamento</h3>
      <div>
          <p>Plenty of long text description ......</p>
      </div>

    </div>

```

```js

//on script 
$("#accordion).accordion();

```

SORT
----

```js

<ul>
    <li>Ford</li>
    <li>Honda</li>
    <li>BMW</li>
</lu>
```

```js


$("ul").sortable();
```

VALUE SLIDER
------------

Range

```html
 <label for="amount">Price range:</label>
  
<input type="text" id="amount" readonly>
  
<div id="slider-range"></div>

```

```js
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
    
    // Set default values
    $( "#amount" ).val( $( "#slider-range" ).slider( "values", 0 ) +
      "€ - " + $( "#slider-range" ).slider( "values", 1 ) + "€" );
```

DATEPICKER
----------

```html
 
<p>Date: <input type="text" id="datepicker"></p>

```

```js

// -------------------- date Picker
    $("#datepicker").datepicker({
      dateFormat: "yy-mm-dd"
    });


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
```

AUTOCOMPLETE
------------

```html
 <label for="tags">Tags: </label>
  <input id="tags">   
```

obter marcas neste link https://gist.github.com/pcgeek86/78f4cad29dd16961ceeeee654127a0db 
```js

 var availableTags = [
      "Abarth",
		"Alfa Romeo",
		"Aston Martin",
		"Audi",
		"Bentley",
		"BMW",
		"Bugatti",
		"Cadillac",
		"Chevrolet",
		"Chrysler",
		"Citroën",
		"Dacia",
		"Daewoo",
		"Daihatsu",
		"Dodge",
		"Donkervoort",
		"DS",
		"Ferrari",
    ];
    $( "#tags" ).autocomplete({
      source: availableTags
    });
```