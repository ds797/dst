<script>
	import Home from '$lib/svg/Home.svelte';
</script>

<main>
	<a href="/">
		<Home size='2rem' />
	</a>
</main>

<style>
	main {
		width: 100%;
		padding: 1rem;
		background: var(--neutral-low);
		box-sizing: border-box;
	}

	a {
		width: 2rem;
		height: 2rem;
	}
</style>