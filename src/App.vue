<template>
  <div id="app">

		<!-- Wrapper -->
			<div id="wrapper" class="fade-in">

				<!-- Intro -->
					<div id="intro">
						<h1>HAPPY<br />
						HOUR</h1>
						<p></p>

					</div>

				<!-- Header -->
					<header id="header">
						<a href="index.html" class="logo">Massively</a>
					</header>

				<!-- Nav -->
					<nav id="nav">
						<ul class="links">
							<li class="active"><a href="/">Home</a></li>
							<li><a href="/search">Search</a></li>
							<li><a href="/favorites">Favorites
              </a></li>
							<li><a href="/login">Login</a></li>
							<li><a href="/logout">Logout</a></li>
							<li><a href="/signup">Signup</a></li>
						</ul>
						<ul class="icons">
							<!-- <li><a href="#" class="icon brands fa-facebook-f"><span class="label">Facebook</span></a></li> -->
							<li><a href="https://www.linkedin.com/in/alexander-racinski/" class="icon brands fa-linkedin"><span class="label">LinkedIn</span></a></li>
							<li><a href="https://github.com/aracinski2" class="icon brands fa-github"><span class="label">GitHub</span></a></li>
						</ul>
					</nav>

          <router-view />


				<!-- Copyright -->
					<div id="copyright">
						<ul><li>&copy; Untitled</li><li>Design: <a href="https://html5up.net">HTML5 UP</a></li></ul>
					</div>
          <div class="bg fixed" style="transform: none;"></div>
          <a href="#navPanel" id="navPanelToggle" class="">Menu</a>
       
			</div>
  </div>
</template>

<style>
</style>
