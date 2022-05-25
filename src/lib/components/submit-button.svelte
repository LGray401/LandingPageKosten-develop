<script lang="ts">
	export let iconSrc: string;
	export let iconAlt: string;
	export let type: undefined | string = undefined;
</script>

<div class="wrapper">
	<button class="button" {type}>
		<p><slot /><img src={iconSrc} alt={iconAlt} /></p>
	</button>
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

		border: none;

		p {
			color: map-get($colors, 'white');
			padding: 0.3em 0.6em;
			margin: 0;
		}

		img {
			padding-left: 0.5em;

			transition: transform 0.1s;
		}
	}
</style>
