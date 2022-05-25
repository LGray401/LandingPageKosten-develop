<script lang="ts">
	import LogoCarousel from '$lib/components/logo-carousel.svelte';
</script>

<div class="social-proof" id="social-proof">
	<h3 class="social-proof__header">Unsere Kundenpartnerschaften</h3>
	<LogoCarousel>
		<img src="/images/logoipsum.png" alt="client logo" />
		<img src="/images/logoipsum.png" alt="client logo" />
		<img src="/images/logoipsum.png" alt="client logo" />
		<img src="/images/logoipsum.png" alt="client logo" />
		<img src="/images/logoipsum.png" alt="client logo" />
	</LogoCarousel>
</div>

<style global lang="scss">
	@use '../scss/variables' as *;

	.social-proof {
		background-color: lighten(map-get($colors, 'grey'), 30%);

		padding: calc(map-get($margin-primary, 'sm') * 2) 0;

		display: flex;
		flex-direction: column;
	}

	.social-proof__header {
		text-align: center;
		margin: 0 map-get($margin-primary, 'sm') map-get($margin-primary, 'sm');
	}
</style>
