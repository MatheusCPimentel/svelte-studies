<script>
	export let name;
	let theColor = 'black';

	const handleClick = () => {
		theColor = 'orange';
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {theColor}">{theColor} color</p>
	<button on:click={handleClick}>Click here to change to orange!</button>
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