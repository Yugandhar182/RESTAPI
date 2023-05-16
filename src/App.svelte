<script>
    import { onMount } from "svelte";
  
    const endpoint = "https://example.com/api/data";
    let data = [];
  
    onMount(async function() {
      await fetchData();
    });
  
    async function fetchData() {
      try {
        const response = await fetch(endpoint);
        data = await response.json();
      } catch (error) {
        console.error("Failed to fetch data:", error);
      }
    }
  </script>
  
  <main>
    <h1>Click below</h1>
    <p>
      <a href="https://example.com/api/data"><button on:click={fetchData} style="background-color: blue; color: white;">Fetch Data</button>
      </a>
    </p>
  
    
  
    {#if data.length > 0}
      <table>
        <thead>
          <tr>
            {#each Object.keys(data[0]) as key}
              <th>{key}</th>
            {/each}
          </tr>
        </thead>
        <tbody>
          {#each data as item}
            <tr>
              {#each Object.values(item) as value}
                <td>{value}</td>
              {/each}
            </tr>
          {/each}
        </tbody>
      </table>
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
  
    table {
      border-collapse: collapse;
      width: 100%;
    }
  
    th,
    td {
      border: 1px solid #ddd;
      padding: 8px;
      text-align: left;
    }
  
    th {
      background-color: #f2f2f2;
    }
  </style>
  