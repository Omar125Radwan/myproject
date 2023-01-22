<script>
	import Modal from "./Modal.svelte";
	let pepole = [
		{ name: "Amr", beltColor: "orange", age: 17, id: 1 },
		{ name: "Omar", beltColor: "black", age: 23, id: 2 },
		{ name: "Ali", beltColor: "brown", age: 26, id: 3 },
	];
	const handleClick = (id) => {
		pepole = pepole.filter((person) => {
			return person.id != id;
		});
	};
	let showModal = false;
	const toggleModal = () => {
		showModal = !showModal;
	};
</script>

<!-- <Modal message="Hey, I am a prop value" isPromo="{true}"/> -->
<Modal {showModal} on:click={toggleModal}>
	<!-- <h3>Add a New Person</h3> -->
	<form>
		<input type="text" placeholder="name" />
		<input type="text" placeholder="belt color" />
		<button>Add Person</button>
	</form>
	<div slot="title">
		<h3>Add a New Person</h3>
	</div>
</Modal>
<main>
	<button on:click={toggleModal}>Open Modal</button>
	{#each pepole as person (person.id)}
		<div>
			{#if person.beltColor === "black"}
				<p><strong>MASTER NINJAS</strong></p>
			{/if}
			<h4>{person.name}</h4>
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
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
