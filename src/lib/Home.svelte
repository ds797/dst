<script context="module">
	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<script>
	import { slide } from '$lib/js/transition';
	import Arrow from '$lib/svg/Arrow.svelte';
	import Name from '$lib/Name.svelte';

	let hover = false;
</script>

<main>
	<a href="/about">
		<h1 on:mouseenter={() => hover = true} on:mouseleave={() => hover = false}>
			Welcome to <Name />
		</h1>
		{ #if hover }
			<div transition:slide={{ axis: 'width', fade: true }} on:mouseenter={() => hover = true} on:mouseleave={() => hover = false}>
				<Arrow size='3rem' direction='right' />
			</div>
		{ /if }
	</a>
</main>

<style>
	main {
		display: flex;
		justify-content: center;
		align-items: center;
		cursor: pointer;
	}

	a {
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>