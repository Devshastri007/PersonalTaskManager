<script>
	import TaskCard from '$lib/TaskCard.svelte'
	

	let tasks = [
		{ id: 1, title: 'Task 1', status: 'Completed' },
    { id: 2, title: 'Task 2', status: 'In Progress' },
    { id: 3, title: 'Task 3', status: 'Not Started' },
    // Add more tasks as needed
  ];
</script>


<svelte:head>
	<title>Task Card</title>
	<meta name="description" content="Task Card" />
</svelte:head>

<div class="text-column">
	<TaskCard />
</div>
