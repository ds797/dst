<script>
	export let title = '', body = '';
</script>

<main>
	<div>
		<slot />
	</div>
	<h3>{title}</h3>
	<p>{body}</p>
</main>

<style>
	main {
		width: 15rem;
		padding: 2rem;
		display: flex;
		flex-flow: column;
		justify-content: center;
		align-items: center;
		gap: 1rem;
		background: var(--neutral-low);
		border-radius: 1rem;
	}

	div {
		width: 6rem;
		height: 6rem;
	}

	div > :global(svg) {
		width: 100%;
		height: 100%;
	}

	p {
		min-height: 6rem;
	}
</style>