<script>
	async function randomDoggie() {
		const res = await fetch('https://dog.ceo/api/breeds/image/random');
		const json = await res.json();
		if (res.ok) {
			return json.message;
		} else {
			throw new Error(json.message);
		}
	}
	let promise = randomDoggie();
	function handleClick() {
		promise = randomDoggie();
	}
</script>

<div>
	{#await promise}
		<p>...loading...</p>
	{:then src}
		<img {src} alt="Puppy!" />
	{:catch error}
		<p style="color: red">{error.message}</p>
	{/await}
	<button on:click={handleClick}>Random Puppy</button>
</div>

<style>
	img {
		height: 100px;
		width: auto;
		display: block;
		margin: 0 auto;
		padding: 10px;
	}
</style>
