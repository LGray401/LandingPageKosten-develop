<script lang="ts">
	import Button from '$lib/components/offer-button.svelte';
</script>

<div class="steps" id="steps">
	<h2 class="steps__header">Unsere 3-Schritte-Erfolgsformel</h2>
	<h2 class="steps__subheader">Ihr Weg zur optimalen SQL Server Performance</h2>
	<div class="steps__wrapper">
		<div class="steps__element">
			<div class="steps__graphic">
				<img
					src="/images/Kick-Off-Meeting-sql-Performance.png"
					alt="Clipboard"
					class="steps__image-center"
				/>
				<img src="/images/hex.svg" alt="Hexagon" class="steps__image-hex" />
				<img src="/images/hex_filled.svg" alt="Hexagon" class="steps__image-side" />
				<img src="/images/arrow_right.svg" alt="Pfeil" class="steps__arrow-right" />
			</div>
			<div class="steps__textblock">
				<h2>1. Kickoff-Meeting</h2>
				<p>
					Gemeinsam beleuchten wir die Problemfelder Ihres Systems sowie bereits durchgeführte
					Maßnahmen und definieren die Ziele plus Projektschritte für Ihr Optimierungsvorhaben.
				</p>
			</div>
		</div>
		<div class="steps__element">
			<div class="steps__graphic">
				<img
					src="/images/systemanalyse-sql-performance.png"
					alt="Clipboard"
					class="steps__image-center"
				/>
				<img src="/images/hex.svg" alt="Hexagon" class="steps__image-hex" />
				<img src="/images/hex_filled.svg" alt="Hexagon" class="steps__image-side" />
				<img src="/images/arrow_left.svg" alt="Pfeil" class="steps__arrow-left" />
			</div>
			<div class="steps__textblock">
				<h2>2. Systemanalyse</h2>
				<p>
					Einsatz unserer Performance-Experten und SQL-Analyse-Tools: Wir führen alle Ergebnisse aus
					dem Kick-Off und der Systemanalysen zusammen. Es entsteht Ihr individuelles
					Optimierungskonzept, welches Bottlenecks kennzeichnet und konkrete Handlungsbedarfe
					bestimmt.
				</p>
			</div>
		</div>
		<div class="steps__element">
			<div class="steps__graphic">
				<img
					src="/images/Optimierungskonzept-sql-server-strategy.png"
					alt="Clipboard"
					class="steps__image-center"
				/>
				<img src="/images/hex.svg" alt="Hexagon" class="steps__image-hex" />
				<img src="/images/hex_filled.svg" alt="Hexagon" class="steps__image-side" />
			</div>
			<div class="steps__textblock">
				<h2>3. Optimierung</h2>
				<p>
					Im finalen Workshop besprechen wir die Ergebnisse des Optimierungskonzepts und beraten Sie
					hinsichtlich der Umsetzung. Dank dieses Wissenstransfers können Sie Ihre
					performanceoptimierte SQL-Server-Umgebung umgehend realisieren.
				</p>
			</div>
		</div>
		<Button href="#contact" iconSrc="/images/arrow.svg" iconAlt="Pfeil" rotation="up"
			>Ihre Anfrage senden</Button
		>
	</div>
</div>

<style lang="scss">
	@use '../scss/variables' as *;
	@use '../scss/mixins' as *;

	.steps {
		/* background-color: lighten(map-get($colors, 'grey'), 30%); */
		background-color: map-get($colors, 'white');
	}

	.steps__header {
		margin: 0;
		padding: map-get($margin-secondary, 'sm') map-get($margin-primary, 'sm');

		text-align: center;

		background-color: map-get($colors, 'red');
		color: map-get($colors, 'white');
	}

	.steps__subheader {
		text-align: center;
		text-transform: none;

		color: map-get($colors, 'red');
	}

	.steps__wrapper {
		display: flex;
		flex-direction: column;
		gap: calc(map-get($margin-primary, 'sm') * 2);

		padding: map-get($margin-primary, 'sm') map-get($margin-primary, 'sm')
			calc(map-get($margin-primary, 'sm') * 2);
	}

	.steps__element {
		display: flex;
		align-items: center;

		&:nth-child(even) {
			flex-direction: row-reverse;

			.steps__graphic {
				margin: 0 calc(map-get($margin-primary, 'sm') * (-1)) 0 map-get($margin-primary, 'sm');

				.steps__image-side {
					left: unset;
					right: -4.2em;
					top: 7.3em;
				}
			}
		}
	}

	.steps__graphic {
		position: relative;
		margin: 0 map-get($margin-primary, 'sm') 0 calc(map-get($margin-primary, 'sm') * (-1));

		@include drop-shadow;

		.steps__image-center {
			position: absolute;
			left: 50%;
			top: 4.5em;
			transform: translate(-50%, -50%);
			width: 75px;
		}

		.steps__image-hex {
			padding-bottom: 8em;
		}

		.steps__image-side {
			position: absolute;
			left: -4.2em;
			top: 7.3em;
		}
	}

	.steps__arrow-left {
		position: absolute;
		bottom: 0;
		left: 0;
	}

	.steps__arrow-right {
		position: absolute;
		right: 0;
		bottom: 0;
	}

	.steps__textblock {
		min-width: 0;
		h2 {
			text-transform: none;
			color: map-get($colors, 'red');

			margin: 0;
		}

		p {
			margin: 0.5em 0 0 0;
		}
	}
</style>
