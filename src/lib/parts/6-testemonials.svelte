<div class="testemonials">
	<div class="testemonials__element">
		<img src="/images/DanielHeinemann.jpg" alt="Rotger Wesener" />
		<div class="testemonials__textblock">
			<p>
				<i
					>„Die Performance-Datenbankprobleme wurden nicht nur gelöst, sondern sind bis heute nicht
					mehr aufgetreten.“</i
				>
			</p>
			<h3>Daniel Heinemann</h3>
			<p>CEO bei CONUTI</p>
		</div>
	</div>
	<div class="testemonials__element hidden">
		<img src="/images/MichaelGraf.jpg" alt="Rotger Wesener" />
		<div class="testemonials__textblock">
			<p>
				<i
					>„sqlXpert liefert alle Daten zu den Ursachen der Performance-Engpässe und bietet konkrete
					Lösungsansätze.“</i
				>
			</p>
			<h3>Michael Graf</h3>
			<p>CEO bei LeBit Software & Consult GmbH</p>
		</div>
	</div>
	<div class="testemonials__element hidden">
		<img src="/images/RotgerWesener.jpg" alt="Rotger Wesener" />
		<div class="testemonials__textblock">
			<p>
				<i
					>„Durch den schlanken und effektiven Lösungsprozess konnten wir Optimierungspotentiale
					identifizieren.“</i
				>
			</p>
			<h3>Rotger Wesener</h3>
			<p>CEO bei b1d1 GmbH</p>
		</div>
	</div>
</div>

<style global lang="scss">
	@use '../scss/variables' as *;

	.testemonials {
		background-color: lighten(map-get($colors, 'grey'), 30%);
		padding: calc(map-get($margin-primary, 'sm') * 2) map-get($margin-primary, 'sm');
	}

	.testemonials__element {
		display: flex;
		align-items: center;

		&.hidden {
			display: none;
		}

		img {
			min-width: 6em;
			border-radius: 100%;
		}
	}

	.testemonials__textblock {
		p,
		h3 {
			text-align: center;
		}

		h3 {
			margin-bottom: 0;
		}
		p {
			margin: 0;
		}
	}
</style>
