<script>
	export let name;
	let theColor = 'black';
	let firstName = 'Matheus';
	let lastName = 'Pimentel'

	$: fullName = `${firstName} ${lastName}`;
</script>

<main>
	<p style="color: {theColor}">{fullName}: {theColor} color</p>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	<input type="text" bind:value={theColor}>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>