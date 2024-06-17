<script>
	import TaskCard from '$lib/TaskCard.svelte'
	import welcome from '$lib/images/svelte-welcome.webp';
	import welcome_fallback from '$lib/images/svelte-welcome.png';
    import { onMount } from 'svelte';
	

	let tasks = [
		{ id: 1, title: 'Task 1', status: 'Completed' },
    { id: 2, title: 'Task 2', status: 'In Progress' },
    { id: 3, title: 'Task 3', status: 'Not Started' },
    // Add more tasks as needed
  ];


  
  function deleteTask() {
    // Implement delete logic here
    console.log(`Deleting task`);
    
  }

  function editTask() {
    // Implement edit logic here
	
    console.log(`Editing task`);
   
  }

  function addNewTask() {

	window.location.href = `/tasks/add`;
    console.log('Adding new task');
  }

  /**
     * @param {number} taskId
     */
  function viewTask(taskId) {
    // Navigate to task details page
    window.location.href = `/tasks/${taskId}`;
  }
</script>


<svelte:head>
	<title>All Task</title>
	<meta name="description" content="All Task" />
</svelte:head>

<div class="task-list">

	<button style="margin-bottom: 10px;" on:click={addNewTask}>
	   ADD TASK <!-- FontAwesome plus icon -->
	  </button>
	  
	
	<table class="table table-striped">
	  <thead>
		<tr>
			<th>Task ID</th>
			<th>Task Title</th>
			<th>Status</th>
			<th>Actions</th>
		
	  </thead>
	  <tbody>
		{#each tasks as task}
		<tr>
			<td>{task.id}</td>
			<td>{task.title}</td>
			<td>{task.status}</td>
			
			<td>

				<button class="btn btn-sm btn-info" on:click={() => viewTask(task.id)}>
					View
				  </button>
				<button class="btn btn-sm btn-danger" on:click={(e) => console.log(e) }>
				 Delete
				</button>
				<button class="btn btn-sm btn-primary ml-2" on:click={(e) => console.log(e) }>
				Edit
				</button>
			  </td>

		  </tr>
		{/each}
	  </tbody>
	</table>
  
	
  </div>

  <style>
	.task-list {
	  margin: 1rem 0;
	}
	table {
	  width: 100%;
	  border-collapse: collapse;
	}
	th, td {
	  padding: 0.5rem;
	  text-align: left;
	  border: 1px solid #ddd;
	}
	th {
	  background-color: #f4f4f4;
	}
  </style>


