<script>
	import { onMount } from 'svelte';
	import { createGrid } from 'gridjs';
	import axios from 'axios';
  
	let data = [];
  
	onMount(async function() {
	  try {
		const response = await axios.get('https://api.recruitly.io/api/job?apiKey=TEST64518616D4CF145D4E20BD47169EA7229BA3');
		data = response.data.data;
	  } catch (error) {
		console.error('Failed to fetch data:', error);
	  }
	});
  
	function createDataGrid() {
	  if (data.length > 0) {
		const grid = createGrid({
		  data,
		  columns: Object.keys(data[0]).map((key) => ({ name: key, title: key })),
		});
  
		grid.render(document.getElementById('data-grid'));
	  }
	}
  </script>
  
  <main>
	<h1>Data Grid</h1>
	<button on:click={createDataGrid}>Load Data</button>
	<div id="data-grid" />
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
  