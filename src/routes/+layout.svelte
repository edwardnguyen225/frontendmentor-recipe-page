<script>
	import '../app.css';
	import '@fontsource-variable/outfit';
	import '@fontsource/young-serif';
</script>

<svelte:head>
	<title>Frontend Mentor | Recipe page</title>
</svelte:head>

<slot />

<style>
	:global(body) {
		font-family: 'Outfit', Arial, Helvetica, sans-serif;
		font-size: 16px;
		line-height: 150%;
		color: var(--wenge-brown);
		background-color: var(--eggshell);
		transition: all 0.2s ease-in-out;
	}

	@media only screen and (min-width: 455px) {
		:global(body) {
			display: flex;
			justify-content: center;
			align-items: center;
			padding: calc(0.085 * 100vw) calc(0.085 * 100vw);
		}
	}
</style>
