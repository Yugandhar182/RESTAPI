<h1>hello</h1>
<script>
	import Grid from "gridjs-svelte";
  
	const data = [
	  { Name: "Sachin", Runs: 320000, Age: 40, Centuries: 100,  Wickets: 168 },
	  { Name: "Kohli", Runs: 25000, Age: 34, Centuries: 75, Wickets: 78 },
	  { Name: "Root", Runs: 19000, Age: 33, Centuries: 45, Wickets: 98 },
	  { Name: "Smith", Runs: 17000, Age: 32, Centuries: 41, Wickets: 119 },
	  { Name: "Pointing", Runs: 22000, Age: 37, Centuries: 65, Wickets: 68 },
	  { Name: "Kane", Runs: 18000, Age: 37, Centuries: 35, Wickets: 61 },
	  { Name: "Anderson", Runs: 2000, Age: 39, Centuries: 0, Wickets: 678 },
	  { Name: "Warne", Runs: 1800, Age: 39, Centuries: 0, Wickets: 778 },
	];
  
	const columns = ["Name", "Runs", "Age", "Centuries", "Wickets"];
	
  
  </script>
  
  <Grid data={data} 
  sort 
  search 
  pagination={{ enabled: true, limit: 3 }} columns={columns} />
  
 
 
  
  <style global>
	@import "https://cdn.jsdelivr.net/npm/gridjs/dist/theme/mermaid.min.css";
  </style>