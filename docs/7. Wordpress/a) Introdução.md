O [wordpress](https://wordpress.com) é um *Content Management System* baseado em php que disponibiliza um interface gráfico de desenvolvimento de páginas com base em temas e plugins.
Pode ser criada uma conta no site wordpress.com, o site desenvolvido será público, ou efectuar um desenvolvimento privado, na nossa máquina local, que mais tarde poderá ser enviado para um serviço de hosting.

## Instalação

1. Descarregar a última versão do wordpress em [wordpress.org](https://wordpress.org/download/).
2. Mover a pasta wordpress para o directoria htdocs do mamp. Neste caso o wordpress vai estar disponível em `http://localhost/wordpress`. Num cenário de alojamento num serviço de hosting a instalação deverá estar ao nível da root. O equivalente numa instalação local seria colocar o conteúdo da pasta wordpress diretamente dentro da pasta htdocs
3. Criar schema e utilizador na base dados. O wordpress vai necessitar de aceder a um schema de bd através de um utilizador.
	1. Aceder a ao [phpMyAdmin](http://localhost/phpMyAdmin/?lang=en).
	2. Criar o schema `wordpress-db`através da opção New*.
	3. Criar o user na tab User Accounts com todos os privilégios e dar acesso ao schema anterior.
	4. Alterar as credenciais de acesso à bd no ficheiro `wp-config-sample.php`:
	```php
		define( 'DB_NAME', 'wordpress-db' );
	
		/** Database username */
		define( 'DB_USER', 'wordpress-user' );
	
		/** Database password */
		define( 'DB_PASSWORD', 'wordpress-pwd' );
	```
	5. Renomear o ficheiro `wp-config-sample.php` para `wp-config.php`.

A partir daqui podemos iniciar a instalação do wordpress acedendo ao endereço `http://localhost/wordpress`

![[Pasted image 20231110124907.png|400]]

Avançar, preencher o form com os dados do site e utilizador, para finalizar a instalação.

## Estrutura

A estrutura do wordpress é baseada em páginas templates que definem o layout do site:
- Header
- Sidebar / menu
- Content
- Footer
Em termos de conteúdo o wordpress pode conter páginas ou posts.

### Páginas

Um website poderá usar [páginas](https://wordpress.com/support/pages/) para criar as página do site tais como por exemplo a home, sobre, contactos. As páginas são estáticas e não estão associadas a uma data ou hora, são locais permanente no site que os utilizadores podem aceder a qualquer altura. São normalmente listadas no [menu](https://wordpress.com/support/menus/)  do site  O endereço tem tipicamente a seguinte forma:
 `http://meu-dominio.com/nome-pagina/`

### Posts

Os posts são elementos individuais de conteúdo do site que estão relacionados com um determinado período no tempo, tal como por exemplo artigos, noticias ou outras atualizações que queremos disponibilizar no site.

O [url](https://wordpress.com/support/permalinks-and-slugs/) de um post tem a seguinte estrutura: `https://yourgroovydomain.com/2024/03/17/post-title/`

Os posts podem ser apresentados de diversas formas num site. Podem ser apresentados de forma resumida numa lista, agrupada por categoria, ou apresentados de forma individual.

## Adicionar páginas

O wordpress permite de uma forma fácil e simples criar novas páginas usando templates pré-definidos no tema default que estamos a usar.
Para adicionar página podemos usar o dashboard na secção Pages.

![[Pasted image 20231113160935.png]]
Quando adicionamos uma página ela é automaticamente adicionada ao menu do site. O nome da página é assumido por feito também no menu.
Se quisermos gerir manualmente o menu de navegação e os respetivos links temos de efetuar estas alteração através do secção Appearance / Editor. Aqui podemos gerir o layout do site e efetuar alterações à sua estrutura. No caso do menu manual podemos ir à seção Navigation e efectuar o detach do mesmo.