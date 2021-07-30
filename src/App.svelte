<script>
	import Modal from './Modal.svelte';

	let people = [
		{name: 'Yoshi', beltColor: 'black', age: 25, id: 1},
		{name: 'Mario', beltColor: 'orange', age: 45, id: 2},
		{name: 'Loshi', beltColor: 'black', age: 35, id: 3}	
	];
	const deletePerson = (id) => {
		people = people.filter((person) => person.id != id);

	}

	let num = 5;	
</script>
<Modal />
<main>
	{#each people as person (person.id)}
		<div>
			<h4>{person.name}</h4>
			{#if person.beltColor === 'black'}
				<p><strong>Master Ninja</strong></p>
			{/if}
			<p>{person.age} years old, {person.beltColor} belt. </p>
			<button on:click={() => {deletePerson(person.id)}}>Delete Person</button>
		</div>
	{:else}
		<p>There are no people to show...</p>
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