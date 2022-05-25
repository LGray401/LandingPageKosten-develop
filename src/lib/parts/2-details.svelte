<div class="details" id="details">
	<h2 class="details__header">Wir garantieren Ihnen optimale IT-Kosten</h2>
	<div class="details__wrapper">
		<div class="details__element">
			<div class="details__graphic">
				<img
					src="/images/Kick-Off-Meeting-sql-Performance.png"
					alt="Clipboard"
					class="details__image-center"
				/>
				<img src="/images/hex.svg" alt="hexagon" class="details__image-hex" />
				<div class="details__check">
					<svg
						width="58"
						height="51"
						viewBox="0 0 58 51"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M3.27527 24.8146C13.3876 33.2416 19.2865 41.6685 19.2865 41.6685C19.2865 41.6685 32.7697 19.3371 54.2584 5.01123"
							stroke="white"
							stroke-width="10"
						/>
					</svg>
				</div>
			</div>
			<div class="detail__textblock">
				<h2>Lizenzkosten</h2>
				<p>
					Wir erschließen bei ihnen das vollständige Potenzial Lizenzkosten zu senken. Das erreichen
					wir durch die Optimierung von Systemen und Software, Cloud- bzw. On-Prem Lösungen und
					Datenanalyse-basierter Investitionen.
				</p>
			</div>
		</div>
		<div class="details__element">
			<div class="details__graphic">
				<img
					src="/images/Kick-Off-Meeting-sql-Performance.png"
					alt="Clipboard"
					class="details__image-center"
				/>
				<img src="/images/hex.svg" alt="hexagon" class="details__image-hex" />
				<div class="details__check">
					<svg
						width="58"
						height="51"
						viewBox="0 0 58 51"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M3.27527 24.8146C13.3876 33.2416 19.2865 41.6685 19.2865 41.6685C19.2865 41.6685 32.7697 19.3371 54.2584 5.01123"
							stroke="white"
							stroke-width="10"
						/>
					</svg>
				</div>
			</div>
			<div class="detail__textblock">
				<h2>Wissenskosten</h2>
				<p>
					Senken Sie die Kosten für ihre IT-Schulungen, nutzen Sie unser digitales Wissen dann, wenn
					es benötigt wird. Unsere Mission zum Thema Wissen: Aktuell, digital, 24/7 & 365 Tage.
				</p>
			</div>
		</div>
		<div class="details__element">
			<div class="details__graphic">
				<img
					src="/images/Kick-Off-Meeting-sql-Performance.png"
					alt="Clipboard"
					class="details__image-center"
				/>
				<img src="/images/hex.svg" alt="hexagon" class="details__image-hex" />
				<div class="details__check">
					<svg
						width="58"
						height="51"
						viewBox="0 0 58 51"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
					>
						<path
							d="M3.27527 24.8146C13.3876 33.2416 19.2865 41.6685 19.2865 41.6685C19.2865 41.6685 32.7697 19.3371 54.2584 5.01123"
							stroke="white"
							stroke-width="10"
						/>
					</svg>
				</div>
			</div>
			<div class="detail__textblock">
				<h2>Ressourcenkosten</h2>
				<p>
					Unsere Self-Services garantieren freie Kapazität für ihren DBA, so dass er mehr
					erledigen-, bzw. sich neuen Aufgaben widmen kann. Dieser Service steht ihnen 24/7 & 365
					Tage zur Verfügung.
				</p>
			</div>
		</div>
	</div>
</div>

<style lang="scss">
	@use '../scss/variables' as *;
	@use '../scss/mixins' as *;

	.details__header {
		margin: 0;
		padding: map-get($margin-secondary, 'sm') map-get($margin-primary, 'sm');

		text-align: center;

		background-color: map-get($colors, 'red');
		color: map-get($colors, 'white');
	}

	.details__wrapper {
		display: flex;
		flex-direction: column;
		gap: calc(map-get($margin-primary, 'sm') * 2);

		margin: calc(map-get($margin-primary, 'sm') * 2) map-get($margin-primary, 'sm');
	}

	.details__element {
		display: flex;
		align-items: center;

		&:nth-child(odd) {
			flex-direction: row-reverse;

			.details__graphic {
				margin: 0 -2.2em 0 map-get($margin-primary, 'sm');
			}

			// shift check arrow to the left on odd elements
			.details__check {
				left: 0;
				right: unset;
			}
		}
	}

	.details__graphic {
		position: relative;
		margin: 0 map-get($margin-primary, 'sm') 0 -2.2em;

		flex-shrink: 0;

		@include drop-shadow;

		.details__image-center {
			position: absolute;
			left: 50%;
			top: 4.5em;
			transform: translate(-50%, -50%);
			width: 75px;
		}

		.details__image-hex {
			padding-bottom: 2em;
		}
	}

	.details__check {
		position: absolute;
		bottom: 1.5em;
		right: 0;

		background-color: map-get($colors, 'green');
		border-radius: 100%;

		svg {
			padding: 0.2em;
		}
	}

	.detail__textblock {
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
