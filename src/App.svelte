<script>
	export let name;
	let beltColor = 'black';
	const handleClick = () => {
		beltColor = 'orange';
	}
	const handleInput = (e) => {
		beltColor = e.target.value;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<h2>{beltColor}</h2>
	<button on:click={handleClick}>update belt color</button>
	<!-- One Way Data Binding -->
	<!-- <input type="text" on:input={handleInput}> -->
	<!-- Two Way Data Binding -->
	<!-- <input type="text" on:input={handleInput} value="{beltColor}"> -->
	<input type="text" bind:value={beltColor}>
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