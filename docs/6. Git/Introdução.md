O [`git`](_https://git-scm.com/_) é uma ferramenta de controlo de versões no desenvolvimento de código. 
Num projeto de desenvolvimento de código a determinada altura vai ser muito importante controlar as alterações e adições que vão ser feitas ao longo do tempo. 

Com o git podemos ver que alterações um ficheiro sofreu ao longo do tempo. Podemos testar determinada soluções e voltar atrás, a um ponto anterior no tempo, sem qualquer esforço. Ou eventualmente ocorreu um erro e queremos desfazer algum do trabalho feito.

O `git` permite aos developers verem a sua timeline de alterações, decisões e progresso de um projecto em apenas um lugar.

## Criar um repositório

Um repositório é uma directoria de projecto que está a ser monitorizada pelo `git`.

Podemos criar um repositório vazio:
```git
# cria a directoria my-repo e inicialia-a com a funções git
git init my-repo
```

ou clonar um repositório online:
```git
# descarrega o repositório do endereço especificado
git clone https://github.com/Ardozia/lsd-layout-portfolio.git
```

A partir deste momento podemos abrir a directoria no editor e começar a trabalhar.
Vamos por exemplo, criar uma página `index.html`
![[Pasted image 20231107185530.png]]
Estas alterações forem detetadas pelo `git`pelo que apenas temos de indicar o ficheiro (ou os ficheiros, * para todos) que vai ser monitorizado e guardar as alterações.

```git
# adiciona o ficheiro para tracking
git add index.html

# confirma as alterações detetadas
git commit -m "added index.html to initial commit"
```
![[Pasted image 20231107190020.png|400]]

## Branches

Vamos imaginar que queremos testar uma solução incrível, mas queremos voltar atrás facil e rapidamente se as coisas não correrem muito bem.
Podemos criar um `branch` e trabalhar sobre ele nesta solução. 

```git
# cria um novo branch
git branch crazy-experiment

# passar a trabalhar neste branch
git checkout crazy-experiment
```

![[Pasted image 20231107191349.png|400]]

Apesar de irmos avançando com a solução incrível, o corpo principal (main) vai manter a versão à data de criação do branch. E vamos poder trocar entre o branch e corpo principal de forma simples e rápida.

Vamos então efectuar algumas modificações no ficheiro `index.html`.
Por exemplo adicionar um parágrafo:
```html
<p>Welcome to the magic of git</p>
```

Depois de gravar vamos novamente adicionar o ficheiro para tracking e confirmar as alterações efetuadas:
```git
# adiciona o ficheiro para tracking
git add index.html

# confirma as alterações detetadas
git commit -m "added welcome subtitle"
```

![[Pasted image 20231107191858.png|400]]

Como podemos observar as alterações ficaram apenas na ramificação do branch `crazy-experiment`, o corpo principal `main` mantém-se no mesmo local. À medida que vamos adicionando mais alterações ao longo do tempo, mais nos vamos afastando do main.

De qualquer forma podemos chegar a um momento em que afinal queremos aplicar as alterações efectuadas no branch `crazy-experiment` ao corpo principal `main`.

Para isso devemos fazer checkout para o `main`e depois efetuar o merge:
```git
# passar a trabalhar no branch main
git checkout main

# juntar o branch crazy-experiment ao main
git merge crazy-experiment
```

![[Pasted image 20231108152611.png|500]]