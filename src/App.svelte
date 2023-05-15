<script>
	import Grid from "gridjs-svelte";
	
	
		const data = [
	  { name: "Sachin", runs: 320000, age: 40, centuries: 100,  wickets: 168 },
	  { name: "Kohli", runs: 25000, age: 34, centuries: 75, wickets: 78 },
	  { name: "Root", runs: 19000, age: 33, centuries: 45, wickets: 98 },
	  { name: "Smith", runs: 17000, age: 32, centuries: 41, wickets: 119 },
	  { name: "Pointing", runs: 22000, age: 37, centuries: 65, wickets: 68 },
	  { name: "Kane", runs: 18000, age: 37, centuries: 35, wickets: 61 },
	  { name: "Anderson", runs: 2000, age: 39, centuries: 1, wickets: 678 },
	  { name: "Warne", runs: 1800, age:39, centuries: 2, wickets: 778 },
	];
  
	  

	const columns = ["name", "runs" , "age" , "centuries" , "Wickets"];
	
  

  </script>
  <Grid data={data} 
   sort 
   search 
   pagination={{ enabled: true, limit:5 }}  />

  <style global>
  @import "https://cdn.jsdelivr.net/npm/gridjs/dist/theme/mermaid.min.css";
  </style>
  
