<footer class="footer">
	<div class="footer__address">
		<p>
			<strong>Hauptanschrift:</strong><br />sqlXpert GmbH<br />Alte Jakobstr. 78<br />10179 Berlin
		</p>
		<p>
			<strong>Direkter Kontakt:</strong><br />+49 30 921 49 214<br />info@sqlxpert.de
		</p>
	</div>
	<p><a href="/impressum">Impressum</a></p>
	<p><a href="/dsgvo">Datenschutz</a></p>
</footer>

<style global lang="scss">
	@use '../scss/variables' as *;

	.footer {
		background-color: lighten(map-get($colors, 'grey'), 30%);

		border-top: 0.2em solid map-get($colors, 'red');

		padding: map-get($margin-primary, 'sm');

		display: flex;

		& > * {
			flex: 1;

			text-align: center;
			&:first-child {
				text-align: left;
			}
			&:last-child {
				text-align: right;
			}
		}

		p {
			margin-top: 0;
		}
	}
</style>
