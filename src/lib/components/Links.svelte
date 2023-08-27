<script lang="ts">
	import type { LinkEntry } from '$lib/types/linkentry.type';
	import Link from './Link.svelte';

	export let content: Array<LinkEntry>;
</script>

<div>
	{#each content as { name, url }}
		<Link {url}>{name}</Link>
	{/each}
</div>

<style lang="scss">
	div {
		display: flex;
		flex-flow: column;
		align-items: center;
		width: 80vw;
		padding: 10px 0;
	}
</style>
