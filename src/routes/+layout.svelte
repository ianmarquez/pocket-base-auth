<script>
	import '../app.postcss';
</script>

<nav class="bg-neutral text-neutral-content">
	<div class="max-w-[1440px] mx-auto navbar">
		<div class="navbar-start">
			<a href="/" class="btn btn-ghost text-xl">PB + SK</a>
		</div>
		<div class="navbar-end">
			<ul class="menu menu-horizontal">
				<li><a href="/login">Log In</a></li>
				<li><a href="/register">Register</a></li>
			</ul>
		</div>
	</div>
</nav>

<main class="max-w-[1440px] mx-auto py-8 px-4">
	<slot />
</main>
