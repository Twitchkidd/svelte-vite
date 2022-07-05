<script>
	let count = 0;
	$: doubled = count * 2;
	$: console.log('the count is ' + count);
	$: {
		console.log('the count is ' + count + '!');
		document.getElementById('app').style.background = `hsl(156 0% ${
			100 - count
		}%)`;
	}
	$: if (count === 10) {
		alert('Reload to reset background color!');
	}
	const increment = () => {
		count += 1;
	};
	let name = 'counter';
</script>

<button on:click={increment} {name}>
	Clicks: {count}
</button>
<p>Doubled: {doubled}</p>
{#if count > 5}
	<span>That's a lot of counting!</span>
{:else if count > 0}
	<span>We're counting!</span>
{:else}
	<span>Start counting!</span>
{/if}

<style>
	button {
		font-family: inherit;
		font-size: inherit;
		padding: 1em 2em;
		color: #ff3e00;
		background-color: rgba(255, 62, 0, 0.1);
		border-radius: 2em;
		border: 2px solid rgba(255, 62, 0, 0);
		outline: none;
		width: 200px;
		font-variant-numeric: tabular-nums;
		cursor: pointer;
	}

	button:focus {
		border: 2px solid #ff3e00;
	}

	button:active {
		background-color: rgba(255, 62, 0, 0.2);
	}
</style>
