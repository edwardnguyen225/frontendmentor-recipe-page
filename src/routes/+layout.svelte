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
	}
</style>
