<script>
	import { page } from '$app/stores';
	import { onMount } from 'svelte';

	let link, tooltip;
	let hideTimeout;

	function copyLink(event) {
		event.preventDefault();
		clearTimeout(hideTimeout);
		hideTimeout = setTimeout(() => tooltip.hide(), 1000);
		navigator.clipboard.writeText('play.ageofelysian.com');
	}

	onMount(() => {
		tooltip = new bootstrap.Tooltip(link, {
			trigger: 'click'
		});
	});
</script>

<nav
	class="navbar navbar-expand-sm navbar-dark"
	style="background-image: url('/images/navbar.png')"
>
	<div class="container-fluid">
		<a class="navbar-brand" href="/">
			<img
				src="/images/favicon.png"
				alt=""
				width="38"
				height="38"
				class="d-inline-block align-text-top"
			/>
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
			<a
				href="/"
				class="d-flex"
				data-bs-toggle="tooltip"
				data-bs-placement="bottom"
				title="Copied to clipboard"
				bind:this={link}
				on:click={copyLink}>play.ageofelysian.com</a
			>
		</div>
	</div>
</nav>

<div class="container-sm my-3 pb-5 my-sm-5">
	<slot />
</div>
