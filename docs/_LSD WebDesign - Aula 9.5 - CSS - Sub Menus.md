Menus com submenus em CSS

-definir estrutura

```css
#menuItems {
			font-family: Helvetica;
			color: gray;
		}


		#menuItems ul a {
			text-decoration: none;
			color: gray;
		}

		#menuItems ul li {
			float: left;
			list-style: none;
			position: relative;
			padding: 10px;
		}
		/* Quebra float nos ultimos li p */
		#menuItems ul ul li {
			float: none;
			white-space: nowrap;
		}

		/* Define hover para todos os li que tem um ul por cima 
		div p - Selects all <p> elements inside <div> elements	1
		div > p	- Selects all <p> elements where the parent is a <div> element
		*/
		#menuItems ul li:hover {
			background-color:#f6f6f6
		}

		/* Define o submenu container 
		posição absolute para posicionar face ao seu pai relative
		*/
		#menuItems ul ul { 
			display: none;
			/*Position relative criar espaço para entre li apresentar caixa com o ul de 2º nível*/
			position: absolute;
			padding: 0;  /*   Elimina o espaço a esquerda*/
			background-color: white;
			width: 200px;
			top:100%;
			left:0;
			border: 1px solid black;
		}

		#menuItems ul li:hover > ul {
			display: block;
		}

		


```

HTML
----

```html
	<div id="menuItems">
		<ul>
			<li><a href="">About</a></li>
			<li><a href="">Services</a>
				<ul>
					<li>Webdesign</li>
					<li>Game development</li>
					<li>Consulting</li>
				</ul>
			</li>
			<li><a href="">Products</a>
				<ul>
					<li>Templates</li>
					<li>Fonts</li>
					<li>Backgrounds</li>
				</ul>
			</li>
			<li><a href="">Support</a></li>
			<li><a href="">Contacts</a></li>
		</ul>
	</div>

```

Media queries