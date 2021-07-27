<script>
	let name = 'Chris'; 
	let belt = 'Black';

	const handleClick = () => {
		belt = 'White';
	}

	const handleInput = (e) => {
		belt = e.target.value
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p style="color: {belt}">This is your first Svelte App! Doesn't it look GREAT? Also, I can't believe you are a {belt} belt! </p>
	<!-- <input type="text" on:input={handleInput} value = {belt}> -->
	<input type="text" bind:value = {belt}>
	<button on:click = {handleClick}>Update belt color</button>
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
		font-weight: 800;
	}

	p {
		font-size: 1.5em;
		font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>