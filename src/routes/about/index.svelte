<script context="module">
	import { browser, dev } from '$app/env';
	import Name from '$lib/Name.svelte';
	import Card from '$lib/Card.svelte';
	import Users from '$lib/svg/Users.svelte';
	import Pencil from '$lib/svg/Pencil.svelte';
	import Lightbulb from '$lib/svg/Lightbulb.svelte';

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<svelte:head>
	<title>About</title>
	<meta name="description" content="Learn more about dst" />
</svelte:head>

<main>
	<h1>About <Name /></h1>
	<h3><Name /> private tutoring is based in Marin County, California, specializing in mathematics and computer science.</h3>
	<div>
		<Card title='Individually focused' body='One-on-one learning helps students receive the complete attention they deserve.'>
			<Users />
		</Card>
		<Card title='Written work' body='Students show their work when solving problems, rooting strategies into their minds.'>
			<Pencil />
		</Card>
		<Card title='Tips and tricks' body='Techniques learned through years of experience help accelerate students{'\''} progress.'>
			<Lightbulb />
		</Card>
	</div>
	<h3><a href="/go">Ready?</a></h3>
</main>

<style>
	main {
		flex: 1;
		padding: 2rem;
		display: flex;
		flex-flow: column;
		align-items: center;
		gap: 4rem;
	}

	h1, h3 {
		max-width: 80%;
	}

	div {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 2rem;
	}

	@media (max-aspect-ratio: 1/1) {
		div {
			flex-flow: column;
		}
	}
</style>
