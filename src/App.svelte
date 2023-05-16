<script>
  import { onMount } from "svelte";
  let jsonData = [];

  onMount(async () => {
    const response = await fetch("https://api.recruitly.io/api/job?apiKey=TEST64518616D4CF145D4E20BD47169EA7229BA3");
    const responseData = await response.json();
    jsonData = responseData.data;
  });
</script>

<main>
  <h1>Job applications</h1>
  {#if jsonData.length > 0}
    <div class="grid-container">
      {#each jsonData as item}
        <div class="grid-item">
          <span class="heading">id:</span>
          <span>{item.id}</span>
        </div>
        <div class="grid-item">
          <span class="heading">reference:</span>
          <span>{item.reference}</span>
        </div>
        <div class="grid-item">
          <span class="heading">status:</span>
          <span>{item.status}</span>
        </div>
        <div class="grid-item">
          <span class="heading">industry:</span>
          <span>{item.industry}</span>
        </div>
      {/each}
    </div>
  {/if}
</main>



<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
  }

  .grid-container {
    display: grid;
    grid-template-columns: repeat(4, 1fr); /* Four columns */
    gap: 8px;
    width: 100%;
  }

  .grid-item {
    border: 1px solid #ddd;
    padding: 5px;
    text-align: left;
    display: flex;
    flex-direction: column;
  }

  .heading {
    font-weight: bold;
  }
</style>
