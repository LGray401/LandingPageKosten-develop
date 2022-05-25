<script lang="ts">
	import Button from '$lib/components/offer-button.svelte';
</script>

<div class="ups" id="ups">
	<div class="ups__menu-placeholder" />
	<img
		class="ups__background-image"
		src="/images/BerlinLimitedFineArtPrints-062.jpg"
		alt="berlin skyline"
	/>
	<div class="ups__banner">
		<h1>IT Kosten senken – Performance steigern</h1>
		<p>
			<b><span>X-W</span>atch | <span>X-C</span>ube | <span>X-S</span>ervice</b> Wir garantieren optimale
			Performance für Technik, Organisation und Mensch, verbunden mit der Möglichkeit IT-Kosten zu senken.
		</p>
		<p>
			Mit unserer detaillierten experten- sowie softwarebasierten Analyse optimieren wir
			Datenbanksysteme, bei gleichzeitiger Beurteilung von Hardware- und Lizenzkosten.
		</p>
		<Button href="#contact" iconSrc="/images/arrow.svg" iconAlt="arrow" rotation="down"
			>Ihre Anfrage senden</Button
		>
	</div>
	<div class="ups__tip">
		<svg
			class="ups__tip"
			width="375"
			height="117"
			viewBox="0 0 375 117"
			fill="none"
			xmlns="http://www.w3.org/2000/svg"
			preserveAspectRatio="none"
		>
			<path d="M187.5 0L0 102V117H375V102L187.5 0Z" fill="white" />
		</svg>
		<a href="#details" class="ups__downlink"
			><svg
				width="58"
				height="21"
				viewBox="0 0 58 21"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path d="M3 3L29 18L55 3" stroke="black" stroke-width="5" stroke-linecap="round" />
			</svg>
		</a>
	</div>
</div>

<style global lang="scss">
	@use '../scss/variables' as *;

	.ups {
		position: relative;
		min-height: 100vh;

		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: space-between;
	}

	.ups__menu-placeholder {
		height: map-get($nav-size, 'sm');
	}

	.ups__banner {
		margin: map-get($margin-primary, 'sm');
		padding: map-get($margin-primary, 'sm');
		border-radius: map-get($margin-primary, 'sm');

		background-color: transparentize(map-get($colors, 'white'), 0.2);

		h1:first-child {
			margin-top: 0;

			color: map-get($colors, 'red');
		}

		span {
			color: map-get($colors, 'red');
		}
	}

	.ups__background-image {
		position: absolute;
		width: 100%;
		height: 100%;
		object-fit: cover;

		z-index: -1;
	}

	.ups__tip {
		position: relative;
		width: 100%;
		height: 15vh;

		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.ups__downlink {
		position: absolute;

		bottom: 1em;
	}
</style>
