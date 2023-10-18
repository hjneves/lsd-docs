Exemplo de menu
---------------

```css
body {
	font-family: Montserrat;
	color: white;
	margin: 0;
}

  

a:link, a:visited {
text-decoration: none;
color: white;
}

  

video {
position: fixed;
min-height: 100%;
min-width: 100%;
z-index: -1;
}

#wrapper {
display: flex;
max-width: 768px;
margin: 0 auto;
}

  

#menu {
width: 25%;
}

#menu ul {
list-style: none;
}

#menu ul li {
padding: 4px;
}

#menu ul li:hover {
padding-left: 8px;
}

#content {
width: 75%;
background-color: rgba(0,0,0,0.4);
padding: 6px;
box-sizing: border-box;
}

  

.sectionHeading {
display: flex;
justify-content: space-between;
align-items: center;
}

  
  

#landingMessage{
height: 600px;
display: flex;
justify-content: center;
align-items: center;
}

#products .sectionBody {
display: flex;
justify-content: space-between;
flex-wrap: wrap;
gap: 4px;
}

  

#products .sectionBody div {
flex-grow: 1;
flex-basis: 30%;
background-color: white;
}

.sectionBody p {
text-align: justify;
}

  

.product p {
background-color: gray;
margin: 0;
text-align: center;
padding: 6px;
}

.product img {
height: 100px;
margin: 0 auto;
display: block;
}

.product input {
display: block;
width: 80%;
height: 28px;
text-align: center;
color: white;
border: none;
padding: 8px;
margin: 8px auto;
box-sizing: border-box;
border-radius: 14px;

background: black;
background: linear-gradient(black,gray,black);
cursor: pointer;

}

  

.product input:hover {
background: black;
}

  

.product p:nth-child(3) {
background-color: white;
color: black;
font-size: 1.2em;
}

  

.product div {
height: 100px;
/* background-image: url("images/b1.jpg");*/
background-repeat: no-repeat;
background-position: center center;
}

  

.cell1 {
background-image: url("../images/b1.jpg");
}

  

.cell2 {
background-image: url("../images/b2.jpg");
}
```

HTML
----

```html
<video muted=true autoplay loop>
<source src="media/video.mp4" type="video/mp4">
</video>

  

<div id="wrapper">

	<!-- Menu -->
	<div id="menu">
	
		<ul>
		<li><a href="">About</a></li>
		<li><a href="">Products</a></li>
		<li><a href="">Services</a></li>
		<li><a href="">Support</a></li>
		</ul>
	
	</div>
	
	<!-- Content -->
	<div id="content">
		<!-- LandingMessage -->
		<div id="landingMessage">
			<h2>
			<i class="fa fa-quote-left"></i>
			Ballon air trips
			<i class="fa fa-quote-right"></i>
			</h2>
		</div>

		<!-- Services -->
		<div>
			<div class="sectionHeading">
				<h2>Services</h2>
				<a href=""><i class="fa fa-chevron-circle-up"></i></a>
			</div>
			<div class="sectionBody">
				<p>
			It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).
				</p>
			</div>
		</div>
		
		<!-- Products -->
		<div id="products">
		
			<div class="sectionHeading">
			
				<h2>Products</h2>
				
				<a href=""><i class="fa fa-chevron-circle-up"></i></a>
			
			</div>
			
			
			<div class="sectionBody">
			
				<div class="product">
					<p>Cartoon</p>
					<div class="cell1"></div>
					<p>120€</p>
					<form>
						<input name="" type="submit" value="BUY">
					</form>
				</div>
				
				<div class="product">
				
					<p>Cartoon</p>
					<div class="cell2"></div>
					<p>120€</p>
					<form>
						<input name="" type="submit" value="BUY">
					</form>
				
				</div>
				
				<div class="product">
				
					<p>Cartoon</p>
					
					<img src="images/b3.jpg">
					
					<p>120€</p>
				
					<form>
						<input name="" type="submit" value="BUY">
					</form>
				
				</div>
				
				<div class="product">
				
					<p>Cartoon</p>
					
					<img src="images/b1.jpg">
					
					<p>120€</p>
				
					<form>
						<input name="" type="submit" value="BUY">
					</form>
				
				</div>
				
				<div class="product">
				
					<p>Cartoon</p>
					
					<img src="images/b2.jpg">
					
					<p>120€</p>
				
					<form>
						<input name="" type="submit" value="BUY">
					</form>
				
				</div>
				
				<div class="product">
				
					<p>Cartoon</p>
					
					<img src="images/b3.jpg">
					
					<p>120€</p>
				
					<form>
						<input name="" type="submit" value="BUY">
					</form>
				
				</div>
			
			  
			
			</div>
		
		</div>
		
		<!-- Support -->
		
		<div>
		
		<div class="sectionHeading">
		
			<h2>Support</h2>
		
			<a href=""><i class="fa fa-chevron-circle-up"></i></a>
		
		</div>
		
		<div class="sectionBody">
		
			<p>
			
			It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. The point of using Lorem Ipsum is that it has a more-or-less normal distribution of letters, as opposed to using 'Content here, content here', making it look like readable English. Many desktop publishing packages and web page editors now use Lorem Ipsum as their default model text, and a search for 'lorem ipsum' will uncover many web sites still in their infancy. Various versions have evolved over the years, sometimes by accident, sometimes on purpose (injected humour and the like).
			
			</p>
		
		</div>
	
	</div>
	
	  
	
	</div>

  

</div>
```