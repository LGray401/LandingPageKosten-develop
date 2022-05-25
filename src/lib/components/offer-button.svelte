<script lang="ts">
	export let href: string;
	export let iconSrc: string;
	export let iconAlt: string;
	export let rotation: string;

	let up = false;
	let down = false;
	if (rotation === 'up') up = true;
	if (rotation === 'down') down = true;
</script>

<div class="wrapper">
	<a class="button" {href}>
		<p><slot /><img src={iconSrc} alt={iconAlt} class:up class:down /></p>
	</a>
</div>

<style lang="scss">
	@use '../scss/variables' as *;
	@use '../scss/mixins' as *;

	.wrapper {
		display: flex;
		justify-content: center;
	}

	.button {
		background-color: map-get($colors, 'red');
		border-radius: 0.3em;

		@include drop-shadow;

		p {
			color: map-get($colors, 'white');
			padding: 0.3em 0.6em;
			margin: 0;
		}

		img {
			padding-left: 0.5em;

			transition: transform 0.1s;
		}

		&:hover {
			.up {
				transform: rotate(-90deg) translate(-30%, 30%);
			}
			.down {
				transform: rotate(90deg) translate(-15%, -30%);
			}
		}
	}
</style>
