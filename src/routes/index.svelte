<script context="module">
	export const prerender = true;
</script>

<script>
  import { writable } from 'svelte/store';
  
  let textValue = writable("");
  let counter = writable(0);
  
  let countValue, text;

  counter.subscribe(value => {
    countValue = value;
  });
  
  textValue.subscribe(value => {
    text = value;
  });

  function updateCounter(){
    const newCount = text.trim().split(" ").length;
    $counter = newCount;
  }
  
</script>

<svelte:head>
	<title>Word Counter by motcodes</title>
</svelte:head>

<section>
	<h1>Word Counter</h1>
	<p>{countValue}</p>
	<textarea bind:value={text} on:input={updateCounter} id="wordCounter" name="wordCounter" rows="20" cols="50"/>
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
