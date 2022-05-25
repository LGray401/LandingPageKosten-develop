<script lang="ts">
	import { onMount } from 'svelte';

	let innerWidth: number;
	let animate: boolean;
	let carousel: any;

	const onResize = () => {
		animate = carousel.offsetWidth > innerWidth;
		console.log(animate);
	};

	// animation parameters
	let offset: number;
	let offsetStr = '0px';
	let pixelPerS = 30;
	let paused = false;
	onMount(() => {
		// set initial values
		offset = carousel.offsetWidth / 2;
		// check whether to animate once
		onResize();
		// attach to resize
		window.addEventListener('resize', onResize);

		// sliding animation
		let lastTimestamp = 0;
		let animation = requestAnimationFrame(function update(timestamp: number) {
			if (animate && !paused) {
				offset -= pixelPerS * ((timestamp - lastTimestamp) / 1000);
				if (offset <= -carousel.offsetWidth / 2) {
					offset = carousel.offsetWidth / 2;
				}
			} else if (!paused) {
				offset = 0;
			}
			offsetStr = `${Math.trunc(offset)}px`;

			lastTimestamp = timestamp;

			animation = requestAnimationFrame(update);
		});

		return () => {
			window.removeEventListener('resize', onResize);
			cancelAnimationFrame(animation);
		};
	});
</script>

<svelte:window bind:innerWidth />

<div
	class="carousel"
	on:pointerenter={() => {
		paused = true;
	}}
	on:pointerleave={() => {
		paused = false;
	}}
>
	<div class="carousel__wrapper" style="--offset:{offsetStr}">
		<div class="carousel__duplicate" bind:this={carousel}><slot /></div>
		{#if animate}
			<div class="carousel__duplicate"><slot /></div>
		{/if}
	</div>
</div>

<style lang="scss">
	@use '../scss/variables' as *;

	.carousel {
		overflow-x: hidden;
		display: flex;
		justify-content: center;
	}

	.carousel__wrapper {
		display: flex;
		align-items: center;
		padding: 0 map-get($margin-primary, 'sm');

		transform: translateX(var(--offset));
	}

	.carousel__duplicate {
		display: flex;
		align-items: center;
	}
</style>
