<script>
	import Grid from "svelte-gridjs-component";
	import { onMount } from "svelte";
  
	const endpoint = "https://api.recruitly.io/api/job?apiKey=TEST64518616D4CF145D4E20BD47169EA7229BA3";
	let data = [];
  
	onMount(async function() {
	  try {
		const response = await fetch(endpoint);
		data = await response.json();
	  } catch (error) {
		console.error("Failed to fetch data:", error);
	  }
	});
  </script>
  
  <main>
	<h1>Click below</h1>
	<p><a href="https://api.recruitly.io/api/job?apiKey=TEST64518616D4CF145D4E20BD47169EA7229BA3">fetching the information</a></p>
  
	{#if data.length > 0}
	  <Grid {data} />
	{/if}
  </main>
  
  <style>
	main {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	  padding: 20px;
	}
  
	h1 {
	  margin-bottom: 20px;
	}
  </style>
  