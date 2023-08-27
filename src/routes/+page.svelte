<script lang="ts">
	import config from '$lib/config.json';
	import Header from '$lib/components/Header.svelte';
	import Links from '$lib/components/Links.svelte';

	// window is not available during server-side rendering
	const isBrowser = () => typeof window !== 'undefined';
	// Set vh for css trick for phone devices
	// https://css-tricks.com/the-trick-to-viewport-units-on-mobile/
	isBrowser() &&
		document.documentElement.style.setProperty('--vh', `${window.innerHeight * 0.01}px`);
</script>

<svelte:head>
	<title>{config.title}</title>
</svelte:head>

<main>
	<Header>{config.name}</Header>
	<Links content={config.links} />
</main>

<style lang="scss">
	$gradient1: #26455a;
	$gradient2: #457b7d;

	main {
		display: flex;
		flex-flow: column;
		flex-grow: 1;
		align-items: center;
		background-image: linear-gradient(205deg, $gradient1, $gradient2);

		// Backup for devices not supporting Custom Properties
		min-height: 100vh;
		// Trick for phone devices to count vh only from available viewport, not whole screen
		// https://css-tricks.com/the-trick-to-viewport-units-on-mobile/
		min-height: calc(var(--vh, 1vh) * 100);
	}
</style>
