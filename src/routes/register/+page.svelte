<script>


	import Register from '$lib/Register.svelte'
	

	
</script>


  <style>
	.text-column {
	  max-width: 600px;
	  margin: 0 auto;
	  padding: 20px;
	  font-family: Arial, sans-serif;
	}
  
	h1 {
	  font-size: 2em;
	  margin-bottom: 20px;
	}
  
	a {
	  display: inline-block;
	  margin-top: 20px;
	  padding: 10px 20px;
	  color: #fff;
	  background-color: #007BFF;
	  text-decoration: none;
	  border-radius: 4px;
	  transition: background-color 0.3s ease;
	}
  
	a:hover {
	  background-color: #0056b3;
	}
  
	section {
	  margin-bottom: 20px;
	}
  </style>

<svelte:head>
	<title>About</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div class="text-column">
	<h1>Personal Task Manager </h1>
<section>

	<Register />
	</section>
<a href="/login">Login </a>
	
</div>

