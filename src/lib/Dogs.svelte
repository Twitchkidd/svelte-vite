<script>
	let dogs = [
		{ name: 'Cooper', temperment: 'Sassy' },
		{ name: 'Harley', temperment: 'Monstrous' },
		{ name: 'Dawa', temperment: 'Zen' },
	];
	function minusDog() {
		dogs = dogs.slice(1);
	}
</script>

<ul>
	<!-- #each dogs as dog -->
	<!-- #each dogs as { name, temperment }, i -->
	<!-- if the list item was a component that got props in ... start from keys and go back over everything from there oh no I only hit like a quarter of the api lol -->
	{#each dogs as { name, temperment }, i (i)}
		<li>{i + 1}: {name} the {temperment}</li>
	{/each}
</ul>
<button on:click={minusDog}>Remove dog</button>

<style>
	li {
		list-style: none;
	}
</style>
