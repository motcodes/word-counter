<script context="module">
	export const prerender = true;
</script>

<script>
	let textValue = "";

   const countWords = () => textValue.split(' ').length;
   console.log(countWords());
    
	let counterValue = countWords() || 0;
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<h1>Word Counter</h1>
	<p>{counterValue}</p>
	<textarea bind:value={textValue} on:change={countWords} id="wordCounter" name="wordCounter" rows="20" cols="50"/>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}

</style>
