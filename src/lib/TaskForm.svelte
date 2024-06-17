<script>
    import { onMount } from 'svelte';
	

	let title = '';
	let description = '';
	let status = '';
	let dueDate = '';
	let category = '';
  
	/**
     * @param {{ preventDefault: () => void; }} event
     */
	function handleSubmit(event) {

		
	  event.preventDefault();
  
	  // Validate and handle form submission here
	  const taskData = {
		title,
		description,
		status,
		dueDate,
		category
	  };

	  onMount(async () => {

		fetch('https://jsonplaceholder.typicode.com/tasks', {
  method: 'POST',
  body: JSON.stringify({
    title: taskData.title,
    body: taskData.description,
    status: taskData.status,
	dueDate: taskData.dueDate,
    category: taskData.category,

  }),
  headers: {
    'Content-type': 'application/json; charset=UTF-8',
  },
})
  .then((response) => response.json())
  .then((json) => console.log(json));





	  }



	  )
  
	  console.log('Submitted task data:', taskData);
    	alert("Thanks -- Form submitted");
	  // Reset form fields after submission (optional)
	  resetForm();
	}
  
	function resetForm() {
	  title = '';
	  description = '';
	  status = '';
	  dueDate = '';
	  category = '';
	}
  </script>
  
  <style>
	/* Optional: Add styling for the form */
	.task-form {
	  max-width: 400px;
	  margin: auto;
	}
  
	.form-control {
	  margin-bottom: 10px;
	}

	.task-form {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    background-color: #f9f9f9;
  }

  .form-group {
    margin-bottom: 15px;
  }

  .form-group label {
    font-weight: bold;
  }

  .form-control {
    width: 100%;
    padding: 8px;
    font-size: 1rem;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-sizing: border-box;
  }

  .form-control:focus {
    outline: none;
    border-color: #007bff;
    box-shadow: 0 0 0 0.2rem rgba(0, 123, 255, 0.25);
  }

  .btn-primary {
    background-color: #007bff;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  .btn-primary:hover {
    background-color: #0056b3;
  }
  </style>
  
  <form class="task-form" on:submit={handleSubmit}>
	<div class="form-group">
	  <label for="title">Title</label>
	  <input type="text" id="title" class="form-control" bind:value={title} required>
	</div>
	<div class="form-group">
	  <label for="description">Description</label>
	  <textarea id="description" class="form-control" bind:value={description}></textarea>
	</div>
	<div class="form-group">
	  <label for="status">Status</label>
	  <select id="status" class="form-control" bind:value={status} required>
		<option value="">Select status</option>
		<option value="Not Started">Not Started</option>
		<option value="In Progress">In Progress</option>
		<option value="Completed">Completed</option>
	  </select>
	</div>
	<div class="form-group">
	  <label for="dueDate">Due Date</label>
	  <input type="date" id="dueDate" class="form-control" bind:value={dueDate}>
	</div>
	<div class="form-group">
	  <label for="category">Category</label>
	  <input type="text" id="category" class="form-control" bind:value={category}>
	</div>
	<button type="submit" class="btn btn-primary">Submit</button>
  </form>
  