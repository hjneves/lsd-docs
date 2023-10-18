# O que é?

- linguagem de programação
- permite dar ao site interactividade e dinamismo

## Iniciar

Criar página nova com base numa existente (pixar.html da aula52 de CSS)

### Adicionar javascript inline (não é o recomendado actualmente)

```html
  <button onClick="alert('Hi There');">Submit</button><
```

### Adicionar javascript na tag script

```html
<script type="text/javascript">

  alert("Page Loaded");

</script>
```

Neste caso todo o código é executado quando a página é carregada

Por convenção é colocado no em:

* final do HEAD
* imediantamente antes do final do BODY

### Aceder aos elementos HTML

`document` - estrutura que contém toda a página web
`id e class` - usados para identificar elementos em Javascript
`innerHTML` -  propriedade que contem o HTML do elemento

```html
 <p class="text">Some text</p>
 <p>Article 1</p>

  <script type="text/javascript">
  
    // This is a comment
  
    /*
     This is a multi-line
     comment
    */
    
	// querySelector - returns the first element within the document that matches the specified selector,

    alert(document.querySelector(".text").innerHTML);    
    document.querySelector(".text").innerHTML="Some more text";
    document.getElementsByTagName("p")[0].innerHTML="Some more text";
    
  </script>

```

## Evento de Click - button
---------------

### usando uma função anónima

```html
<button id="checkCart">Cart</button>
  <script type="text/javascript">
    
    document.querySelector("#checkCart").onclick=function() {
      alert("Hi! You have 5 products on the cart");
    }
    
</script>
```

### usando uma função normal

```html
<button id="checkCart" onclick="validateCart()">Cart</button>

<script type="text/javascript">
    
    // alternative method
    document.querySelector("#checkCart").onclick=validateCart
    
    function validateCart() {
      alert("Hi You don't have any products");
    }
    
</script>
```

### Usar um botão para mudar conteudo

```html
  <button class="submit">Enviar</button>
  <p class="text">Work 1.pdf</p>



  <script type="text/javascript">  
    document.querySelector(".submit").onclick = function () {
      document.querySelector(".text").innerHTML = "Work 1.pdf (enviado)";
      // Neste caso até era melhor usar appending
      // Versão curta do appending
      document.querySelector(".text").innerHTML += " (enviado)";

    }

  </script>
```

### Usar um botão para mudar conteudo com código HTML

```html

	span {
		color:green;
	}

  <button class="submit">Enviar</button>
  <p class="text">Work 1.pdf</p>



  <script type="text/javascript">  
    document.querySelector(".submit").onclick = function () {

      document.querySelector(".text").innerHTML += " <span>(enviado)<span>";

    }
</script>
```

### Alterar o style de um elemento

Fazer o increase e o decrease da fonte de uma página

```html

<button class="inc">Increase</button>
<button class="dec">Decrease</button>
<p>My Portfolio Works</p>

<script type="text/javascript">
let size = 100;
let p = document.querySelector("p");

 document.querySelector(".inc").onclick = function () {
	 size = size + 2 
	 p.style.fontSize = size + "%";            
}

document.querySelector(".dec").onclick = function () {
	 size = size - 2 
	 p.style.fontSize = size + "%";            
}

</script>

```

### DESAFIO: Criar 2 temas de cores para aplicar

1º criar 2 botões
2º criar um onclick para cada um deles

```js

    document.getElementById("myBtnTemaA").onclick = function () {

      document.getElementById("text").innerHTML = "<p>LSD WebDesign</p><ul><li>Design</li><li>Programação</li></ul>";
      document.getElementById("text").style.border = "1px blue solid";
      document.getElementById("text").style.color = "blue";

    }
   document.getElementById("myBtnTemaB").onclick = function () {

      document.getElementById("text").innerHTML = "<p>LSD WebDesign</p><ul><li>Design</li><li>Programação</li></ul>";
      document.getElementById("text").style.border = "1px green solid";
      document.getElementById("text").style.color = "green";

    }
```

### VARIÁVEIS e INPUTS

Criar variáveis -\> Usar uma variável como parâmetro da função getElementById
Criar INPUT —\> Usar o texto do campo de input para alimentar o conteudo do \<p\>

```html
  <input id="myInput" type="text" value="LSD"/>
  <button id="myBtn">Submit</button>
  <p id="text">LSD WebDesign</p>


  <script type="text/javascript">
    
    var myText = "text";
    var myContent; // começar por colocar aqui o document get element do myInput

    document.getElementById("myBtn").onclick = function () {
            myContent = document.getElementById("myInput").value;
            document.getElementById(myText).innerHTML = myContent;
    }

  </script>
```


### APRESENTAR LISTA DE CURSOS em UL

- input é um array copm nomes de curso
- usa createElement e appendChild

```html

  <style>
  li.item{
    list-style-type: square; padding:5px;
  }
  </style>


<div id="schoolCourses"></div>
  

  <script type="text/javascript">
    var ul = document.createElement('ul');
        ul.setAttribute('id','courses');
    
        courseList = ['Web Design','Game Design','Design de Interiores','Design de Moda'];
        
        document.getElementById('schoolCourses').appendChild(ul);
     
        courseList.forEach(renderProductList);
    
        function renderProductList(element) {
            var li = document.createElement('li');
            li.setAttribute('class','item');           
            li.innerHTML = element;
            ul.appendChild(li);
        }
    
  </script>

```