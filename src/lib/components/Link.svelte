<script lang="ts">
	export let url: string;
</script>

<a href={url}><slot /></a>

<style lang="scss">
	a {
		font-size: 15px;
		padding: 20px 0;
		text-align: center;
		background-color: #eee;
		width: 90%;
		min-width: 150px;
		max-width: 500px;
		font-variation-settings: 'wght' 420;
		margin: 10px 0;
		border-radius: 5px;
		box-shadow: 0 4px 17px -9px rgba(0, 0, 0, 1);

		&:link,
		&:visited,
		&:active {
			color: #222;
			text-decoration: none;
		}

		&:hover {
			color: #111;
		}
	}
</style>
