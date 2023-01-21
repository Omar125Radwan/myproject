<script>
	import Modal from "./Modal.svelte";
	let pepole = [
		{name: 'Amr', beltColor: 'orange', age: 17, id: 1},
		{name: 'Omar', beltColor: 'black', age: 23, id: 2},
		{name: 'Ali', beltColor: 'brown', age: 26, id: 3},
	];
	const handleClick = (id) => {
		pepole = pepole.filter((person) => {
			return person.id != id;
		});
	};
	let num = 4;
</script>

<Modal />
<main>
	{#each pepole as person (person.id)}
		<div>
			{#if person.beltColor === 'black'}
				<p><strong>MASTER NINJAS</strong></p>
			{/if}
			<h2>{person.name}</h2>
			<p>{person.beltColor}</p>
			<p>{person.age} years old</p>
			<button on:click={() => handleClick(person.id)}>delete</button>
		</div>
	{:else}
		<p>There is No pepoles</p>
	{/each}
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
