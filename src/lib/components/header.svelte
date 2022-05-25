<script>
	let active = false;
</script>

<header class="header">
	<div class="header__wrapper">
		<a href="/" class="header__logo"
			><img src="/images/sqlXpert-Logo_rgb.png" alt="sqlxpert Logo" /></a
		>
		<nav
			class="header__nav"
			class:active
			on:click={() => {
				active = false;
			}}
		>
			<h2><a href="/#details">Produktdetails</a></h2>
			<h2><a href="/#contact">Kontakt</a></h2>
			<h2><a href="/#">Über uns</a></h2>
		</nav>
		<div
			class="hamburger"
			class:active
			on:click={() => {
				active = !active;
			}}
		>
			<span />
			<span />
			<span />
		</div>
		<div class="header__shadow" class:active />
	</div>
</header>

<style global lang="scss">
	@use '../scss/variables' as *;
	@use '../scss/mixins' as *;

	.header {
		height: map-get($nav-size, 'sm');

		background-color: map-get($colors, 'white');

		position: fixed;
		left: 0;
		top: 0;
		right: 0;

		z-index: 1;
	}

	.header__shadow {
		position: absolute;
		inset: 0;

		@include box-shadow;

		pointer-events: none;

		transition: opacity 0.5s ease;
		&.active {
			opacity: 0;
		}
	}

	.header__wrapper {
		box-sizing: border-box;
		padding: map-get($margin-primary, 'sm');

		width: 100%;
		height: 100%;

		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.header__logo {
		height: 100%;

		img {
			height: 100%;
		}
	}

	.header__nav {
		display: flex;
		gap: map-get($margin-primary, 'sm');

		background-color: map-get($colors, 'white');

		h2 {
			margin: 0;
		}

		a {
			color: map-get($colors, 'grey');

			&:hover {
				color: map-get($colors, 'black');
			}

			@media (hover: none) {
				// text-decoration: underline;
				color: map-get($colors, 'black');
			}
		}
	}

	.hamburger {
		width: 1.2em;
		height: 1em;

		display: none;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;

		cursor: pointer;

		span {
			width: 100%;
			height: 3px;
			border-radius: 1px;
			background-color: map-get($colors, 'black');

			transition: all 0.5s ease;
		}

		&.active {
			span {
				&:nth-child(1) {
					transform: translateY(0.4em) rotate(45deg);
				}
				&:nth-child(2) {
					opacity: 0;
				}
				&:nth-child(3) {
					transform: translateY(-0.4em) rotate(-45deg);
				}
			}
		}
	}

	// larger screens
	@media only screen and (min-width: $breakpoint) {
		.header {
			height: map-get($nav-size, 'lg');
		}

		.header__wrapper {
			padding: map-get($margin-secondary, 'lg') map-get($margin-primary, 'lg');
		}

		.header__nav {
			gap: map-get($margin-primary, 'lg');
		}
	}

	// smaller screens (mobile menu)
	@media only screen and (max-width: $breakpoint) {
		.header__nav {
			position: fixed;
			inset: 0;

			flex-direction: column;

			padding: map-get($margin-primary, 'sm');
			margin-top: map-get($nav-size, 'sm');

			transform: translateX(-100%);
			transition: transform 0.5s ease;

			&.active {
				transform: translateX(0);
			}
		}

		.hamburger {
			display: flex;
		}
	}
</style>
