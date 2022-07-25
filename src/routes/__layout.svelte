<script context="module"> // Bypass slot reactivity updating both components during transition
	export const load = async ({ url }) => ({ props: { key: url.pathname } })
</script>

<script>
	import '../app.css';
	import Nav from '$lib/Nav.svelte';
	import Transition from '$lib/Transition.svelte';
	import Footer from '$lib/Footer.svelte';

	export let key;
</script>

<main>
	<Nav />
	<div>
		<Transition {key}>
			<slot />
		</Transition>
	</div>
	<Footer />
</main>

<style>
	main {
		width: 100%;
		height: 100%;
		display: flex;
		flex-flow: column;
		justify-content: stretch;
		align-items: stretch;
		background: var(--neutral);
	}

	div {
		flex: 1;
		display: flex;
		flex-flow: column;
		justify-content: stretch;
		align-items: stretch;
		overflow: scroll;
	}
</style>