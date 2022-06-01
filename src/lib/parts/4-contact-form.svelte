<script context="module" lang="ts">
	import type { Load } from '@sveltejs/kit';
	export const load: Load = async ({ url }) => ({ props: { url } });
</script>

<script lang="ts">
	import Button from '$lib/components/submit-button.svelte';
</script>

<div class="contact-form" id="contact">
	<h2 class="contact-form__title">Unverbindliche Kosten-Erstberatung</h2>
	<h2 class="contact-form__subtitle">Kontaktieren Sie uns jetzt!</h2>
	<div class="contact-form__portrait">
		<img class="contact-form__logo" src="/images/sqlXpert-Logo_rgb.png" alt="sqlXpert Logo" />
		<img src="/images/Jeanette_Buechner_resized.jpg" alt="Jeanette Büchner" />
		<div class="contact-form__portrait__text">
			<h2>Jeanette Büchner</h2>
			<h3>Business Development Managerin</h3>
		</div>
	</div>
	<form
		class="contact-form__form"
		name="Kontakt: Lizenzkosten/Wissenskosten/Resourcenkosten"
		method="POST"
		action="/#submitted"
		data-netlify="true"
	>
		<input
			type="hidden"
			name="form-name"
			value="Kontakt: Lizenzkosten/Wissenskosten/Resourcenkosten"
		/>

		<div class="contact-form__dropdown">
			<label class="off-screen" for="gender">Anrede</label>
			<select id="gender" name="anrede" required>
				<option value="Herr">Herr</option>
				<option value="Frau">Frau</option>
				<option value="Andere">Andere</option>
			</select>
		</div>
		<div class="contact-form__text-input">
			<label class="off-screen" for="company">Firma</label>
			<input type="text" id="company" name="firma" placeholder="Firma*" required />
		</div>
		<div class="contact-form__text-input">
			<label class="off-screen" for="firstname">Vorname</label>
			<input type="text" id="firstname" name="vorname" placeholder="Vorname*" required />
		</div>
		<div class="contact-form__text-input">
			<label class="off-screen" for="lastname">Nachname</label>
			<input type="text" id="lastname" name="nachname" placeholder="Nachname*" required />
		</div>
		<div class="contact-form__text-input">
			<label class="off-screen" for="adress">Adresse</label>
			<input type="text" id="adress" name="adresse" placeholder="Adresse*" required />
		</div>
		<div class="contact-form__text-input">
			<label class="off-screen" for="zip">Postleitzahl</label>
			<input type="text" id="zip" name="postleitzahl" placeholder="Postleitzahl*" required />
		</div>
		<div class="contact-form__text-input">
			<label class="off-screen" for="location">Ort</label>
			<input type="text" id="location" name="ort" placeholder="Ort*" required />
		</div>
		<div class="contact-form__text-input">
			<label class="off-screen" for="mail">Email</label>
			<input type="text" id="mail" name="email" placeholder="Email*" required />
		</div>
		<div class="contact-form__text-input">
			<label class="off-screen" for="phone">Telefon</label>
			<input type="text" id="phone" name="telefon" placeholder="Telefon*" required />
		</div>
		<div class="contact-form__text-area">
			<label class="off-screen" for="additional">Ihre Anmerkungen</label>
			<textarea name="anmerkungen" id="additional" placeholder="Ihre Anmerkungen" rows="4" />
		</div>
		<p class="contact-form__data-confirmation">
			<input type="checkbox" id="data" name="datenschutz" required />
			<label for="data"
				>Ich habe die <a href="/#">Datenschutzerklärung</a> zur Kenntnis genommen. Ich stimme zu, dass
				meine Angaben und Daten zur Beantwortung meiner Anfrage elektronisch erhoben und gespeichert
				werden.</label
			>
		</p>
		<Button iconSrc="/images/svgs/envelope.svg" iconAlt="Briefumschlag Icon" type="submit"
			>Anfrage abschicken</Button
		>
	</form>
</div>

<style global lang="scss">
	@use '../scss/variables' as *;

	.contact-form {
		background-color: map-get($colors, 'white');

		margin: calc(map-get($margin-primary, 'sm') * 2) map-get($margin-primary, 'sm');
	}

	h2 {
		margin: 0.5em 0;
	}

	.contact-form__title {
		text-align: center;
	}

	.contact-form__subtitle {
		color: map-get($colors, 'red');
		text-align: center;
		text-transform: none;
	}

	.contact-form__logo {
		max-width: 10em;
		margin: map-get($margin-primary, 'sm');
	}

	.contact-form__portrait {
		position: relative;

		display: flex;
		flex-direction: column;
		align-items: center;

		width: 100%;

		img {
			width: 100%;
		}

		&:hover {
			.contact-form__portrait__text {
				transform: translateY(1em);
				h3 {
					opacity: 0;
				}
			}
		}

		margin-bottom: map-get($margin-primary, 'sm');
	}

	.contact-form__portrait__text {
		position: absolute;
		bottom: map-get($margin-secondary, 'sm');
		left: map-get($margin-secondary, 'sm');
		right: map-get($margin-secondary, 'sm');

		transform: translateY(0);
		transition: transform 0.3s;
		h3 {
			opacity: 1;
			transition: opacity 0.3s;
		}

		h2,
		h3 {
			text-transform: none;
			text-align: center;
			margin: 0.3em 0;

			color: map-get($colors, 'white');
		}
	}

	.off-screen {
		// get the labels off screen
		position: absolute;
		left: -1000em;
	}

	.contact-form__form {
		display: flex;
		flex-direction: column;
		align-items: stretch;

		gap: map-get($margin-secondary, 'sm');

		p {
			margin: 0 0 map-get($margin-secondary, 'sm');
		}
	}

	.contact-form__text-input,
	.contact-form__dropdown,
	.contact-form__text-area {
		display: flex;
		flex-direction: column;
		align-items: stretch;

		input,
		textarea,
		select {
			padding: map-get($margin-secondary, 'sm');
			background-color: map-get($colors, 'white');
			border: 1px solid map-get($colors, 'grey');
			border-radius: calc(map-get($margin-secondary, 'sm') / 2);
		}

		textarea {
			resize: none;
		}
	}
</style>
