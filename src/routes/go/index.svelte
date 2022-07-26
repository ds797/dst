<script context="module">
	import { browser, dev } from '$app/env';
	import Name from '$lib/Name.svelte';
	import Card from '$lib/Card.svelte';
	import Dollar from '$lib/svg/Dollar.svelte';
	import Mail from '$lib/svg/Mail.svelte';

	// we don't need any JS on this page, though we'll load
	// it in dev so that we get hot module replacement...
	export const hydrate = dev;

	// ...but if the client-side router is already loaded
	// (i.e. we came here from elsewhere in the app), use it
	export const router = browser;

	// since there's no dynamic data here, we can prerender
	// it so that it gets served as a static asset in prod
	export const prerender = true;
</script>

<svelte:head>
	<title>Explore</title>
	<meta name="description" content="Learn more about dst" />
</svelte:head>

<main>
	<h1>Let's get started</h1>
	<h3>To schedule sessions, email <a href="mailto:ds.blue797@gmail.com">ds.blue797@gmail.com</a></h3>
	<div>
		<Card title='Pricing' body='Tutoring starts at $25 per session. Want more? Commissions accepted.'>
			<Dollar />
		</Card>
		<Card title='Contacting' body='Before sending, make sure your email includes your general location and desired sessions per week.'>
			<Mail />
		</Card>
	</div>
	<h3>Want to learn more about the creator of <Name />? Visit <a target="_blank" href="https://797.pages.dev">ds797's home page</a>.</h3>
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