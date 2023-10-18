# Pensamento Computacional

Pensamento Algorítmico
Avaliação
Decomposição
Abstração
Generalização

# Exemplos Javascript

usar o https://codesandbox.io/ para realizar os testes
usar o <https://codepen.io> para realizar os testes.

## Exemplo 1 - variáveis básicas

```js
<!DOCTYPE html>
<html lang="pt">
	<head>
		<meta charset="utf-8">
		<title>Lógica de Programação</title>
		<script>

			/* numéricas */
			let numero1 = 324;
			let numero2 = 234;

			console.log( numero + numero2 );
			console.log( numero - numero2 );
			console.log( numero * numero2 );
			console.log( numero / numero2 );
			console.log( numero % numero2 );

			/* Cálculo da idade */
			let anoNasc = 1980;
			console.log(2023-1980)

			/* String ou texto */
			let nome = "Rui";

			/* Bool */
			let winner = true;

			console.log(nome);
			console.log(winner):

		</script>
	</head>
	<body>
	</body>
</html>
```

## Exemplo 2 - Construir frases dinâmicas

```js
<!DOCTYPE html>
<html lang="pt">
	<head>
		<meta charset="utf-8">
		<title>Lógica de Programação</title>
		<script>
			/* conceito de concatenação */
			const cumprimento = "Olá, ";
			
			// get user from login
			let username = "Ivo"; 

			/* Olá [nome] */
			console.log("Olá " + nome );
		</script>
	</head>
	<body>
	</body>
</html>
```

## Exemplo 3 - Prioridade

```js
<!DOCTYPE html>
<html lang="pt">
	<head>
		<meta charset="utf-8">
		<title>Lógica de Programação</title>
		<script>
			/* conceito de prioridade */

			console.log( "Hoje é dia " + 14 + 2 );
			console.log( "Hoje é dia " + (14 + 2) );
		</script>
	</head>
	<body>
	</body>
</html>
```

## Exemplo 4 - Comparações

```js
<!DOCTYPE html>
<html lang="pt">
	<head>
		<meta charset="utf-8">
		<title>Lógica de Programação</title>
		<script>
			/*
			  operadores de comparação:
			    ==
			    !=
			    <
			    >
			    <=
			    >=

			  vocês têm uma aplicação que pede a idade do
			  utilizador e se o utilizador for maior ou
			  igual a 13 pode registar-se
			  
			*/

			let idade = 20;

			if(idade >= 13) {
				console.log("Podes avançar com registo");
			}
			else {
				console.log("Tens de ter no mínimo 13 anos");
			}
		</script>
	</head>
	<body>
	</body>
</html>
```

```js
---------------------------------- Com várias condições 
<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Várias condições no mesmo IF</title>
        <script>
            /* várias condições no mesmo IF */
            let idade = 13;
            let emailRegistered = true;
            
            if( idade >= 13 && emailRegistered == false ) {
                console.log("Podes avançar com o registo");
            }
            
            if( idade < 13 || emailRegistered == true ) {
                console.log("Tens menos de 13 anos ou o teu email já está registado");
            }
          </script>

    </head>
    <body>
    </body>
</html>
```

## Exercicio 5 - Número aleatório

```js
<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Adivinhar o número</title>
        <script>
            let numero_aleatorio = Math.ceil( Math.random() * 30);
            let resposta = prompt("Adivinhe o número (1 a 30)");
            
            if(resposta == numero_aleatorio) {
                console.log("Acertaste");
            }
            else if(numero_aleatorio > resposta) {
              console.log("Falhaste. O número aleatorio era maior que " + resposta);
            } 
            else {
                console.log("Falhaste. O número aleatorio era menor que " + resposta);
            }

        </script>
    </head>
<body>

    </body>
</html>
```

## Exercicio 6 - Arrays

```js
<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Arrays</title>
        <script>
            let animal1 = "Camelo";
            let animal2 = "Gato";
            let animal3 = "Cavalo";
            let animal4 = "Zebra";
            let animal5 = "Iguana";
            
            let animais = ["Camelo", "Gato", "Cavalo", "Zebra", "Iguana","Tubarão", "Coelho", "Furão"];
            console.log( animais[4] );
            console.log( animais[2] );
            console.log( animais[6] );
            animais[8] = "Cão";
            animais[3] = "Macaco";
        </script>
    </head>
    <body>
    </body>
</html>
```

## Exercício 7 - Ciclos / Loops
```js
<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Repetição de acções</title>
        <script>
            let alarme = 2;
            if(alarme >= 1) {
                console.log("Alarme está a tocar");
	        }
	
	            if(alarme >= 2) {
	                console.log("Alarme está a tocar");  
	        }
	
	            if(alarme >= 3) {
	                console.log("Alarme está a tocar");
	        }
	
	            if(alarme >= 4) {
	                console.log("Alarme está a tocar");
	        } 
        </script>

    </head>
    <body>
    </body>
</html>


// --------  While e for

<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Repetição de acções</title>
        <script>
            let alarme = 4;
            /*
                ciclo é composto por três coisas:
                um início
                um fim ou condição para parar
                um incremento ou uma maneira de chegar ao fim
			*/

            let i = 1; /* <- isto é o início */
            while(i <= alarme) { /* isto é a condição */
                console.log("Alarme está a tocar");
                i = i + 1; /* isto é o incremento */
            }

			for(let i = 1; i <= alarme; i = i + 1) {
                console.log("Alarme está a tocar outra vez");
			} 
</script>

    </head>
    <body>
    </body>
</html>



// -------- Desafio lista números pares até 20

<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Ciclos</title>
        <script>
        /*
            criar um ciclo que mostra os números de 2 em 2 até chegar a 20
        */
        let i = 2;
        while(i <= 20) {
            console.log(i);
            i = i + 2; 
        }

        for(let i = 2; i <= 20; i = i + 2) {
            console.log(i);
        } 
        </script>
</head>
<body>
</body>
</html>
```

## Percorrer um array

```js

// -------- Percorrer os elementos de um array

<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Ciclos for</title>
        <script>
            var friends = ["Ana", "Miguel", "Jaime", "Maria", "Marta"];
            
             for (item of friends) {
                console.log( item );
            }
        </script>
    </head>
<body>
</body>
</html>

/* ------------ Desafio: criar um array com nomes de produtos e depois criar um conjunto de parágrafos com os nomes
por ex. 
  ['vela', 'pilha', 'lápis']

	<p>vela</p>
	<p>pilha</p>
	<p>lápis</p>

*/
<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Ciclos</title>
    <script>

        let products = ['vela', 'pilha', 'lápis'];
        for(item of products) {
                console.log( '<p>' + item + '</p>' );
        }

        </script>
    </head>
    <body>
    </body>
</html>
```

## Ex.  número aleatório

```js
// ------------ Número aleatório

<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Adivinhar o número aleatório</title>
        <script>
            var aleatorio = Math.ceil(Math.random() * 10);
            var resposta = prompt("Adivinhe o número");
            while(resposta != aleatorio) {
                resposta = prompt("Errado, tente de novo");
            }

            alert("Acertaste!");
        </script>
</head>
<body>

    </body>
</html>


-------- 17

<!DOCTYPE html>
<html lang="pt">
    <head>
        <meta charset="utf-8">
        <title>Adivinhar o número aleatório</title>
        <script>
            var aleatorio = Math.ceil(Math.random() * 10);
            var tentativas = 1;
            var resposta = prompt("Adivinhe o número");
            while(resposta != aleatorio) {
                tentativas++;
                if(tentativas > 5) {
                    alert("GAME OVER");
                    break;
                }

                resposta = prompt("Errado, tente de novo");
            }
            if(resposta == aleatorio) {
                alert("Acertaste e utilizaste " + tentativas + "tentativas");
            }
        </script>
    </head>
<body>

    </body>
</html>
```

## Funções

```js

		function greeting() {
			console.log("Olá");
			console.log("Tudo cool?");
			console.log("Bora aí ao café?");
		}

		greeting();
		greeting();
   

        /*
        funções podem opcionalmente receber argumentos ou parametros
        */
		function soma(x, y, verboso) {
			if(verboso == true) {
				console.log("A soma de " +x+ " e " +y+ " é " + (x+y));
			}
			else {
				console.log(x + y);
			}
		}

		soma(3, 5, false);
		soma(13, 25, true);
		soma(134, 2, true);
```

## Exercicio Avaliador

```js


/* exercício

vão criar uma função que diz a avaliação dos alunos
(Alex, 15)    <=> Alex teve suficiente
(Marta, 7)    <=> Marta teve negativa
(Gustavo, 20) <=> Gustavo teve excelente
(Ana, 16)     <=> Ana teve bom
(Jorge, 10)   <=> Jorge teve suficiente
o output vai dizer algo do genero "Alex teve suficiente" ou "Marta teve
negativa"
0 - 20

0-9   <-> negativa
10-15 <-> suficiente
16-18 <-> bom
19-20 <-> excelente
            */
	function avaliador(nome, nota) {
		if(nota <= 9) {
			var avaliacao = "Negativa";
		}
		else if(nota >= 10 && nota <= 15) {
			var avaliacao = "Suficiente";
		}
		else if(nota >= 16 && nota <= 18) {
			var avaliacao = "Bom";
		}
		else {

			var avaliacao = "Excelente";
		}
		console.log(nome + " teve " + avaliacao);
	}
	avaliador("Alex", 15);
	avaliador("Marta", 7);
	avaliador("Gustavo", 20);
	avaliador("Ana", 16);
	avaliador("Jorge", 10);
	function avaliador2(nome, nota) {
		var avaliacoes = ["Negativa", "Negativa", "Negativa",
"Negativa", "Negativa", "Negativa", "Negativa", "Negativa", "Negativa",
"Negativa", "Suficiente", "Suficiente", "Suficiente", "Suficiente",
"Suficiente", "Suficiente", "Bom", "Bom", "Bom", "Excelente", "Excelente"];
ctt
		console.log(nome + " teve " + avaliacoes[nota] );
	}
	avaliador2("Gustavo", 20);
	avaliador2("Jorge", 10);
        

```

## Objects


### Real Life Objects, Properties, and Methods

In real life, a car is an object. 
A car has properties like weight and color, and methods like start and stop:


![](1B07017004BB8D33B79F9A5BFD60F456.gif)

### Propriedades:
car.name = Fiat
car.model = 500
car.weight = 850kg
car.color = white

### Métodos:
car.start()
car.drive()
car.brake() 
car.stop()

All cars have the same properties, but the property values differ from car to car.
All cars have the same methods, but the methods are performed at different times.

---

JavaScript Objects
------------------

You have already learned that JavaScript variables are containers for data values.
This code assigns a simple value (Fiat) to a variable named car: 

`var car = "Fiat";`

Objects are variables too. But objects can contain many values. 
This code assigns many values (Fiat, 500, white) to a variable named car:

`var car = {type:"Fiat", model:"500", color:"white"};`

The values are written as `name:value` pairs (name and value separated by a colon).
JavaScript objects are containers for named values called properties or methods.

```js

      var nome = "João";
      // ....
      nome = "João Carlos";



      // Objectos 
      // entidade
      // - características
      // - funcionalidades

      var aluno = {
        // características / properties
        name    : "Gonçalo",
        surname : "Marques",
        age   : 25,
        finalGrade    : '',
        // ...
        fullname: function () {
          return this.nome + " " + this.apelido; 
        },
        // funcionalidade / methods
        doExam:   function (examName) {
          return "Estou a fazer exame de " + examName;
        },
        calcFinalGrade: function () {
          // Calculate final grade
          let grade = 16
          this.finalGrade = grade
        }

      }

      console.log(aluno.fullname());
      console.log(nome);


      console.log(aluno.name);
      console.log(aluno.age);

      console.log(aluno.doExam());

      aluno.calFinalGrade();

      console.log(aluno.finalGrade);


```