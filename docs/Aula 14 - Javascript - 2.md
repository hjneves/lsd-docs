### DESAFIO: Criar um selector de cores dinâmico por produto

```html
<img src="https://via.placeholder.com/150/3cb">
<form>
<select class="colors"></select>
</form>
```

```js
var colors = ["Azul", 
             "Branco",
             "verde"];

let sel = document.querySelector(".colors");
colors.forEach(function (color){
    let opt = document.createElement('option');
	  opt.value = color;
	  opt.innerHTML = color;
	  sel.appendChild(opt);
})
```

### VALIDAÇÃO DE CAMPOS DE INPUT 

Por exemplo registo de uma newsletter, validar se o campo está vazio, ou inserção de um comentário numa página de produto.

```html
<form id="newComment">
	<p>Escreva o seu comentário</p>
	<textarea></textarea>
	<p class="error"></p>
	<p>
	<button type="submit" class="btn btn-primary">Inserir</button>
	</p>
</form>
```

```js
document.querySelector("#newComment").addEventListener("submit", function(e) {
          e.preventDefault();
          console.log("Form submitted ...");
          insertComment();
})
        
 function insertComment () {
	console.log("Insert Comment ...");
	// check if textarea is empty
	let textarea = document.querySelector('textarea');

	if (textarea.value.trim() == "") {
	  // show error message
	  document.querySelector('.error').textContent = "Comentário inválido";
	  // add boostsrap alert classes
	  document.querySelector('.error').classList.add('alert', 'alert-danger');
	} else {
	  // cleanup error message <p>
	  document.querySelector('.error').textContent = "";
	  document.querySelector('.error').classList.remove('alert', 'alert-danger');
	  // insert comment into comment list
	  // create an <p> element
	  let comment = document.createElement('p');
	  // set <p> element content to user input
	  comment.textContent = textarea.value;
	  // assign comment to comment List div
	  document.querySelector('.commentList').appendChild(comment)
	}
}

    
```

### DATAS

getDate() Get the day as a number (1-31)
getDay() Get the weekday as a number (0-6)
getFullYear() Get the four digit year (yyyy)
getHours() Get the hour (0-23)
getMilliseconds() Get the milliseconds (0-999)
getMinutes() Get the minutes (0-59)
getMonth() Get the month (0-11)
getSeconds() Get the seconds (0-59)
getTime() Get the time (milliseconds since January 1, 1970)

Mostrar alguns exemplos

```html
 <h2>Dia actual:</h2>
 <h2 id="myDay"></h2>
 <button id="myBtn">Submit</button>

  <script type="text/javascript">
    document.getElementById("myBtn").onclick = function () {
      document.getElementById('myDay').innerHTML =  new Date();
    }
  </script>
```

### DESAFIO

Inserir o post com a data no seguintes formato: **1 de Março de 2016**
Formatar p com styles

## Plugin dayjs

`<script src="https://unpkg.com/dayjs@1.8.21/dayjs.min.js"></script>`
`<script src="https://unpkg.com/dayjs@1.8.21/locale/pt.js"></script>`


1. Inserir post com data no formato 1 de Março de 2016
2. formatar a data para o formatocom há x dias atrás.

```js

function insertComment () {
            console.log("Insert Comment ...");
            // check if textarea is empty
            let textarea = document.querySelector('textarea');

            if (textarea.value.trim() == "") {
              // show error message
              document.querySelector('.error').textContent = "Comentário inválido";
              // add boostsrap alert classes
              document.querySelector('.error').classList.add('alert', 'alert-danger');
            } else {
              // cleanup error message <p>
              document.querySelector('.error').textContent = "";
              document.querySelector('.error').classList.remove('alert', 'alert-danger');
              // insert comment into comment list
              // create an <p> element
              let comment = document.createElement('p');
              // set <p> element content to user input
              //comment.textContent = textarea.value;
              comment.innerHTML = `<div><p>${textarea.value}</p>
                <p>${dayjs().format('DD [de] MMMM [de] YYYY')}</p></div>`;

              // assign comment to comment List div
              document.querySelector('.commentList').appendChild(comment)
            }

        }
```