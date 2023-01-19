<script>
	let firstName = "Omar";
	let lastName = "Radwan";
	let beltColor = "black";


	// Reactive Values
	$: fullName = `${firstName} ${lastName}`;
	$: {
		console.log(beltColor);
		console.log(fullName);
	}

	const handleClick = () => {
		beltColor = "orange";
	};
</script>

<main>
	<h1 style="color: {beltColor}">{beltColor}</h1>
	<p>{fullName}</p>
	<input type="text" bind:value={firstName}>
	<input type="text" bind:value={lastName}>
	<input type="text" bind:value={beltColor}>
	<button on:click={handleClick}>update belt color</button>
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
