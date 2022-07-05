<script>
	let numbers = [1, 2, 3, 4];
	function addNum() {
		numbers.push(numbers.length + 1);
		numbers = numbers;
		// It's reactive based on variables getting *assigned!*
		// Indirect references don't work! Find the right object
	}
	$: sum = numbers.reduce((t, n) => t + n, 0);
	let options = {
		name: 'numbers',
		type: 'button',
	};
</script>

<p>{numbers.join(' + ')} = {sum}</p>
<button on:click={addNum} {...options}>Add a number</button>
