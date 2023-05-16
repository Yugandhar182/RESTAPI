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
   
  
    {#if jsonData.length > 0}
      <div class="grid-container">
        {#each jsonData as item}
          {#each Object.entries(item) as [key, value]}
            <div class="grid-item">
              <span>{key}: </span>
              <span>{typeof value === 'object' ? JSON.stringify(value) : value}</span>
            </div>
          {/each}
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
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      gap: 8px;
      width: 100%;
    }
  
    .grid-item {
      border: 1px solid #ddd;
      padding: 5px;
      text-align: left;
    }
  </style>
  