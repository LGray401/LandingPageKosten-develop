<script lang="ts">
	// font
	import '@fontsource/nunito-sans';
	// global scss
	import '$lib/scss/global.scss';

	// components
	import Nav from '$lib/components/header.svelte';
	import Footer from '$lib/components/footer.svelte';
</script>

<div class="layout__wrapper">
	<Nav />
	<slot />
	<Footer />
</div>

<style global lang="scss">
	.layout__wrapper {
		overflow-x: hidden;
	}
</style>
