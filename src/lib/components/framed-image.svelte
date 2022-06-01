<script lang="ts">
	let className = '';
	export { className as class };
	export let src: string;
	export let alt: string;
</script>

<div class="wrapper {className}">
	<img class="frame left" src="/images/bracket-left.svg" alt="Linker Rahmen" />
	<img class="frame right" src="/images/bracket-right.svg" alt="Rechter Rahmen" />
	<img class="image" {src} {alt} />
</div>

<style lang="scss"></style>
