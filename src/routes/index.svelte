<script context="module">
	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	// export const prerender = true;
</script>

<script>
	import Transition from '$lib/Transition.svelte'; 
	import Home from '$lib/Home.svelte'; 
</script>

<main>
	<Home />
</main>

<style>
	main {
		flex: 1;
		display: flex;
		flex-flow: column;
		justify-content: center;
		align-items: center;
	}
</style>