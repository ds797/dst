<script>
	import Heart from '$lib/svg/Heart.svelte';
</script>

<main>
	<p>Made with <a href="https://heroicons.com" target="_blank"><Heart color={'#FF7681'} /></a> by <a href="https://github.com/ds797" target="_blank">ds797</a></p>
</main>

<style>
	main {
		width: 100%;
		height: 6rem;
		display: flex;
		flex-flow: column;
		justify-content: center;
		align-items: center;
		background: var(--neutral-low);
	}

	p {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 0.25rem;
	}
</style>