<script>
	import Grid from "gridjs-svelte";
	
	const data = [
	  { name: "Gopi", email: "gopi123@gmail.com"},
	  { name: "Ravi", email: "Ravi@gmail.com"}, 
	  { name: "Surya", email: "Surya34@gmail.com"}, 
	  { name: "Charan", email: "Charan98@gmail.com"}, 
	  { name: "Chandu", email: "Chandu@gmail.com"}, 
	  { name: "Dilli", email: "Dilli34@gmail.com"}, 
	  { name: "Yeswanth", email: "Yesw76@gmail.com"}, 
	  { name: "Ajay", email: "ajay@gmail.com"}, 
	  { name: "Koti", email: "koti098@gmail.com"}, 
	  { name: "Rajesh", email: "raju654@gmail.com"}, 
	];
	const columns = ["Name", "email"];
	
  

  </script>
  <Grid data={data} 
   sort 
   search 
   pagination={{ enabled: true, limit:5 }}  />

  <style global>
  @import "https://cdn.jsdelivr.net/npm/gridjs/dist/theme/mermaid.min.css";
  </style>
  
