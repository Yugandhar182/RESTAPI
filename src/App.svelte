<script>
  import { onMount } from "svelte";
  import Grid from "gridjs-svelte";
  import { createGrid, search, sort, pagination } from "gridjs";

  let jsonData = [];
  let tableVisible = false;

  onMount(async () => {
    await fetchData();
    tableVisible = true;
  });

  async function fetchData() {
    const response = await fetch("https://api.recruitly.io/api/job?apiKey=TEST64518616D4CF145D4E20BD47169EA7229BA3");
    const responseData = await response.json();
    jsonData = responseData.data;
  }

  let grid;

  function gridReady() {
    grid = createGrid();
    grid.search({
      enabled: true
    });
    grid.sort({
      enabled: true
    });
    grid.pagination({
      enabled: true,
      limit: 38
    });
    grid.forceRender();
  }
</script>

<main class="mt-4">
  {#if tableVisible}
    <Grid
      on:gridjs:ready={gridReady}
      data={jsonData}
      columns={Object.keys(jsonData[0])} />
  {/if}
</main>

<style global>
  @import "https://cdn.jsdelivr.net/npm/gridjs/dist/theme/mermaid.min.css";
</style>
