<script>
	const text = 'This is a <strong>quote!</strong>';
	export let quote = "Picking at it won't make it any better";
</script>

<blockquote>{@html text} {quote}</blockquote>

<style>
	blockquote {
		color: rebeccapurple;
	}
</style>
