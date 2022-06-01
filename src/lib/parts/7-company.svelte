<script lang="ts">
	import Image from '$lib/components/framed-image.svelte';
</script>

<div class="company">
	<h2 class="company__title">Unser Unternehmen</h2>
	<h2 class="company__subtitle">Realisierung zukunftsweisender SQL Datenbanklösungen</h2>
	<h3 class="company__section-title"><span>Unsere Mission</span></h3>
	<div class="company__section">
		<Image
			src="/images/sql-optimierung-berlin.jpg"
			alt="Brandenburger Tor"
			class="company__image"
		/>
		<p>
			Unser täglicher Ansporn ist es, gemeinsam mit unseren Kunden innovative und optimale SQL
			Datenbanklösungen zu schaffen. Im Herzen von Berlin sind wir seit 2014 qualifizierter,
			zertifizierter Spezialist für:
		</p>
		<ul>
			<li>Analysen von Systemen, Prozessen und Daten</li>
			<li>Analyse und Optimierung von Performance- & Security-Szenarien</li>
			<li>Entwicklung von datenbankgestützte Softwarelösungen im Microsoft-Umfeld</li>
			<li>Service im Bereich IT- & Netzwerk-Infrastruktur</li>
			<li>Consulting und Training</li>
		</ul>
	</div>
	<h3 class="company__section-title"><span>Unsere Werte</span></h3>
	<div class="company__section">
		<Image src="/images/people-2569234_640.jpg" alt="Team" class="company__image" />
		<p>
			<span>Produktivität</span>. Wir entwickeln mit unseren Kunden vorausschauende
			Lösungsstrategien, damit Probleme erst gar nicht entstehen.
		</p>
		<p>
			<span>Performance Partnerschaft</span>. Wir unterstützen unsere Kunden über Kurz- wie
			Langstrecke, indem wir für sie ihre Wünsche fokussiert realisieren und passgenaue Lösungen für
			ihre zukünftigen Herausforderungen umsetzen.
		</p>
		<p>
			<span>Maximaler Kundennutzen</span>. Bei allen gemeinsamen Projekten garantieren wir die volle
			Transparenz und Übernahme der Verantwortung und sorgen somit für das erfolgreiche Erreichen
			der gemeinsamen Ziele.
		</p>
	</div>
	<h3 class="company__section-title"><span>Unsere Partner</span></h3>
	<div class="company__partners">
		<img src="/images/logoipsum.png" alt="client logo" />
		<img src="/images/logoipsum.png" alt="client logo" />
		<img src="/images/logoipsum.png" alt="client logo" />
		<img src="/images/logoipsum.png" alt="client logo" />
	</div>
</div>

<style global lang="scss">
	@use '../scss/variables' as *;

	.company {
		margin: calc(map-get($margin-primary, 'sm') * 2) map-get($margin-primary, 'sm');
	}

	.company__title {
		text-align: center;
	}

	.company__subtitle {
		text-align: center;
		text-transform: none;

		color: map-get($colors, 'red');
	}

	.company__section-title {
		text-align: center;
		text-transform: none;

		display: flex;
		align-items: center;

		span {
			flex-shrink: 0;
			padding: 0 map-get($margin-secondary, 'sm');
		}

		&::before,
		&::after {
			display: block;
			content: '';
			border-top: 2px solid map-get($colors, 'red');
			width: 100%;
		}
	}

	.company__section {
	}

	.company__image {
		max-width: 100%;
	}
</style>
