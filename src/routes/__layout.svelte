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

<main class='flex'>
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
		background: var(--neutral);
	}

	div {
		flex: 1;
		position: relative;
		overflow: scroll;
	}
</style>