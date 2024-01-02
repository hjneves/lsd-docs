Utilizar uma linguagem de programação implica pensar de forma algoritmica, lógica e completa. A lógica é a forma de encadear raciocínio para atingir um determinado objetivo.
Um algoritmo é uma sequência de passos que levam à execução de uma tarefa.

No trabalho de programação de um projeto é muito importante decompor um problema a resolver em problemas mais pequenos e assim sucessivamente.Permite reduzir a complexidade e aumentar o nível de foco de abstração da solução, isto é, podemos encontrar soluções que podem depois ser aplicadas noutros contextos semelhantes (por ex. a mesma função que valida se um utilizador está logged in, poderá ser utilizada em várias páginas)

Usar por exemplo o [codesandbox](https://codesandbox.io/) para testes.

## Tipos de dados e operações

### Números e strings

```html
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
```

Exemplo: Construção de frases dinâmicas
```html
<script>
	/* conceito de concatenação */
	const cumprimento = "Olá, ";
	
	// get user from login
	let username = "Ivo"; 

	/* Olá [nome] */
	console.log("Olá " + nome );
</script>
```

Atenção à prioridade das operações
```html
<script>
	/* conceito de prioridade */

	console.log( "Hoje é dia " + 14 + 2 );
	console.log( "Hoje é dia " + (14 + 2) );
</script>
```

### Arrays

Os arrays são estruturas que podem guardar outros dados numa lista. Podemos ter arrays de numeros, de strings, de outros arrays, ou de objetos.
São talvez dos objetos mais usados em programação web, porque uma lista é facilmente percorrida para ler os seus valores e existem funções que permitem ler a informação dos arrays de diversas formas.

```html
<script>
	// Em vez de ...
	let animal1 = "Camelo";
	let animal2 = "Gato";
	let animal3 = "Cavalo";
	let animal4 = "Zebra";
	let animal5 = "Iguana";

	// Podemos ter ...
	let animais = ["Camelo", "Gato", "Cavalo", "Zebra", "Iguana","Tubarão", "Coelho", "Furão"];
	console.log( animais[4] );
	console.log( animais[2] );
	console.log( animais[6] );
	animais[8] = "Cão";
	animais[3] = "Macaco";
</script>
```

### Objects

Os objetos são estruturas de dados que permitem organizar a informação através de propriedades e métodos. As propriedades são características que descrevem o objecto, podem ser números, strings, arrays ou outros objectos. Os métodos são funções que fazem parte do objecto e normalmente estão relacionados com acções que se pretendem executar.

Por exemplo, se pretendemos guardar determinado automóvel num objeto quais seriam as propriedades e métodos?  Podíamos ter propriedades como  peso, a marca, a cor ... e como métodos podíamos ter start() e stop().
![](1B07017004BB8D33B79F9A5BFD60F456.gif)

**Propriedades:**
car.name = Fiat
car.model = 500
car.weight = 850kg
car.color = white

**Métodos:**
car.start()
car.drive()
car.brake() 
car.stop()

Todos os carros partilham as mesmas propriedades, mas elas terão naturalmente valores diferentes conforme o automóvel. Os métodos serão os mesmos em todos os carros mas serão executados em alturas diferentes.

### Objetos em javascript

Já sabemos que as variáveis permitem guardar valores numéricos, string, arrays e bool. 
Por exemplo, guardar a marca de um carro,
`var car = "Fiat";`

Os objetos também podem ser guardados em variáveis, mas podem conter diversos valores numa só estrutura.
Por exemplo podemos guardar o nome, o modelo e a cor:
`var car = {type:"Fiat", model:"500", color:"white"};`

Como podemos ver os valores são escritos no formato `propriedade:valor` e estão separados por vírgulas.
Neste exemplo, temos propriedade e métodos de um objeto `aluno`.
```js

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
  console.log(name);
```

## Operadores lógicos

Os operadores lógicos efectuam uma comparação entre dois valores devolvendo um valor verdadeiro ou falso. São normalmente utilizados em condições que determinam seguir um caminho ou outro conforme o resultado da comparação.

```html
<script>
	/*
	  operadores de comparação:
		== e !=
		<  e >			
		<= e >=

	  Ex. uma aplicação que pede a idade do
	  utilizador e se o utilizador for maior ou
	  igual a 13 pode registar-se
	  
	*/

	let idade = 20;

	if(idade >= 13) {
		console.log("Podes avançar com registo");
	}
	else {
		console.log("Tens de ter no mínimo 13 anos");
		// apresenta ecrã de signup
	}
</script>
```

Operadores lógicos `&&`(e)  e `||`(ou). Quando temos duas condições ligadas por um operador `&&` o resultado será verdadeiro se ambas forem verdadeiras. Já no operador `||`basta que uma das condições seja verdadeira para o resultado ser verdadeiro. 
```html
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
```

Exemplo de um mini jogo em que o utilizador tenta adivinhar um número aleatório entre 1 e 10.
O computador seleciona um número aleatório, o utilizador introduz um valor. Ganha se o numero que introduziu é igual ao escolhido pelo computador.
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


## Loops

Sempre que temos uma acção (ou conjunto de acções ) que vai ser necessário repetir um determinado número de vezes, devemos usar um loop (ciclo).
Um loop tem normalmente uma condição de repetição  e um bloco de instruções a repetir, sendo muito usada para percorrer estruturas como array ou objetos
```
// enquanto a condição permanecer válida ele repete os bloco de instruções
loop (condição) {
    // instruções a repetir
}
```

While loop e for loop
```html
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
```


> Desafio: Lista os números pares até 20
>
```html
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

```html
<script>
	var friends = ["Ana", "Miguel", "Jaime", "Maria", "Marta"];
	
	for (item of friends) {
		console.log( item );
	}
</script>
```

>Desafio: Criar um array com nomes de produtos e depois criar um conjunto de parágrafos com por exemplo as seguintes palavras  ['vela', 'pilha', 'lápis']

```html
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

Pegando no mini jogo anterior podemos realizar um upgrade onde damos um número de tentativas para o jogador tentar adivinhar. 
```html
// ------------ Número aleatório v2

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
                alert("Acertaste e utilizaste " + tentativas + " tentativas");
            }
        </script>
    </head>
<body>

    </body>
</html>
```

## Funções

As funções são outra estrutra fundamental na programação. Sempre que temos um determinado conjunto de operações a realizar que pode ser isolado e reaproveitado para outros locais deverá ser criada uma função. Por exemplo, podemos ter uma função para criar uma tabela com uma lista de resultados.
A função porem ter parâmetros de entrada e normalmente devolvem um valor.
São criadas através do termo `function` ou com a sintaxe `=>`designadas de arrow functions e podem ter um nome ou serem anónimas.


```js
 function about(person) {
	let description =
	  "Pessoa de nome " +
	  person.name +
	  " com " +
	  person.age +
	  " anos de idade e profissão " +
	  person.occupation;
	return description;
  }

  // Exemplo de utilização da função
  var person = {
	name: "Marco",
	age: 30,
	occupation: "Developer"
  };

  var personDescription = about(person);

  console.log(personDescription);
```

