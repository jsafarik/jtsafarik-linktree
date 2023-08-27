<script lang="ts">
	import profilePicture from '$lib/profile-picture.jpg';
</script>

<div>
	<img src={profilePicture} alt="Profile" />
	<span><slot /></span>
</div>

<style lang="scss">
	$profile-picture-size: 120px;

	div {
		display: flex;
		flex-flow: column;
		align-items: center;
		margin-top: 20px;
		font-variation-settings: 'wght' 600;

		span {
			margin-top: 15px;
			color: #ddd;
			text-shadow: 0 2px 4px rgba(0, 0, 0, 0.15);
		}

		img {
			border-radius: 100%;
			width: $profile-picture-size;
			height: $profile-picture-size;
			box-shadow: 0 6px 13px -9px rgba(0, 0, 0, 1);
			object-fit: cover;
			object-position: center;
			user-select: none;
			pointer-events: none;
		}
	}
</style>
