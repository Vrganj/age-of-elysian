<script>
	import { page } from '$app/stores';
</script>

<nav class="navbar navbar-expand-sm navbar-dark" style="background-image: url('/navbar.png')">
	<div class="container-fluid">
		<a class="navbar-brand" href="/">
			<img src="/favicon.png" alt="" width="38" height="38" class="d-inline-block align-text-top" />
		</a>
		<button
			class="navbar-toggler"
			type="button"
			data-bs-toggle="collapse"
			data-bs-target="#navbarSupportedContent"
			aria-controls="navbarSupportedContent"
			aria-expanded="false"
			aria-label="Toggle navigation"
		>
			<span class="navbar-toggler-icon" />
		</button>
		<div class="collapse navbar-collapse" id="navbarSupportedContent">
			<ul class="navbar-nav me-auto">
				<li class="nav-item">
					<a class="nav-link" class:active={$page.url.pathname === '/'} href="/">Home</a>
				</li>
				<li class="nav-item">
					<a class="nav-link" class:active={$page.url.pathname === '/blog'} href="/blog">Blog</a>
				</li>
				<li class="nav-item">
					<a class="nav-link" class:active={$page.url.pathname === '/vote'} href="/vote">Vote</a>
				</li>
				<li class="nav-item">
					<a class="nav-link" class:active={$page.url.pathname === '/discord'} href="/discord"
						>Discord</a
					>
				</li>
			</ul>
		</div>
	</div>
</nav>

<div class="container-sm my-3 my-sm-5">
	<slot />
</div>

<nav class="navbar fixed-bottom navbar-dark" style="background-color: #1d1d1d">
	<div class="container-fluid">
		<a class="navbar-brand" href="#">Fixed bottom</a>
	</div>
</nav>
