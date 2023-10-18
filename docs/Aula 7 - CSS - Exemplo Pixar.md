Exemplo de menu
---------------

```css
.main {
width: 75%;
margin: 0 auto;
}

.header {
display: flex;
flex-flow: row;
justify-content: space-between;
align-items: center;
}

.header ul {
padding: 0;
}

.menu li {
display: inline-block;
height: 20px;
box-sizing: border-box;
}

.menu li:hover {
border-bottom: solid 2px orange;
}

form {
position: relative;
}

form button {
position: absolute;
right: 0;
background-color: transparent ;
border: none;
height: 30px;
width: 40px;
border-radius: 15px;
box-sizing: border-box;

}
.search input {
height: 30px;
width: 160px;
border: 1px solid orange;
border-radius: 15px;
box-sizing: border-box;
background-image: url("../images/lupa.png");
background-size: contain;
background-repeat: no-repeat;
background-position: 100% center;
padding-right: 26px;
}

  

.search input:focus{
outline: none;
background-color: orange;
}

.imageHeading {
height: 400px;
background-image: url("../images/pixar-regras.jpg");
background-size: cover;
background-position: center center;
}

.grid {
display: flex;
flex-flow: row;
gap: 1px;
}

  

.grid div {
flex-grow: 1;
flex-basis: 0;
background-color: chocolate;
height: 140px;
padding: 6px;
box-sizing: border-box;
}


.grid div:hover {
/* opacity: 0.5; */
background-color: rgba(210, 105, 30, 0.5);
}

.headingMessage {
height: 180px;
display: flex;
justify-content: space-around;
align-items: center;
}

a:link, a:visited {
color: darkcyan;
text-decoration: none;
}

.footer {
color: red;
}
```

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.2/font/bootstrap-icons.css">

<div class="main">

	<div class="header">
		<div class="menu">
			<ul>
			<li>About</li>
			<li>Services</li>
			<li>Products</li>
			<li>Support</li>
			<li>Contacts...</li>
			</ul>
		</div>
	
		<div class="search">
			<form>
			<input placeholder="Search here ..." type="text" />
			<button type="submit"><i class="bi bi-search"></i></button>	
			</form>
		</div>
</div>

  

<div class="imageHeading">
</div>

  

<div class="grid">
	<div>Info bl blb ipoj bo iaeoia ihei bp iesjpbi srjgb</div>
	<div>News</div>
	<div>Feed</div>
</div>

<div class="headingMessage">
	<h1>New Pixar movie out</h1>
</div>

<div class="footer">
	<a href="//facebook.com/">Facebook</a>
	<span>|</span>
	<a href="//instagram.com/">Instagram</a>
</div>


</div>
  
```