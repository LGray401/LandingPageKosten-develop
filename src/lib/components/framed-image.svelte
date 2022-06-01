<script lang="ts">
	let className = '';
	export { className as class };
	export let src: string;
	export let alt: string;
</script>

<div class="wrapper {className}">
	<img class="image" {src} {alt} />
	<img class="frame left" src="/images/svgs/bracket_left.svg" alt="Linker Rahmen" />
	<img class="frame right" src="/images/svgs/bracket_right.svg" alt="Rechter Rahmen" />
</div>

<style lang="scss">
	.wrapper {
		position: relative;
	}

	.image {
		width: 100%;
		height: auto;
		display: block;
	}

	.frame {
		position: absolute;
		top: -1px;
		height: calc(100% + 2px);
	}

	.left {
		left: -1px;
	}

	.right {
		right: -1px;
	}
</style>
