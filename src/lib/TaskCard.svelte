<script>
	export let task = {
	  title: 'Sample Task',
	  description: 'This is a sample task description.',
	  category: 'General',
	  status: 'Pending'  // Default status
	};
  </script>
  
  <div class="card mb-3">
	<div class="card-body">
	  <h2 class="card-title"><b>TITLE - {task.title}</b></h2>
	  <p class="card-text">DESC -  {task.description}</p>
	  <div class="badge badge-secondary mr-2">CAT - {task.category}</div>
	  <div class="badge" class:badge-success={task.status === 'Completed'} class:badge-warning={task.status === 'Pending'} class:badge-danger={task.status === 'Overdue'}>STATUS - {task.status}</div>
	</div>
  </div>
  
  <style>

.card {
    border: 1px solid #ddd;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    background-color: #fff;
    padding: 15px;
  }

  .card-title {
    font-size: 1.5rem;
    margin-bottom: 0.5rem;
  }

  .card-text {
    color: #555;
    font-size: 1rem;
    margin-bottom: 1rem;
  }

  .badge {
    padding: 0.5rem 1rem;
    font-size: 0.875rem;
    border-radius: 4px;
    margin-right: 5px;
  }

  .badge-secondary {
    background-color: #6c757d;
    color: #fff;
  }

  .badge-success {
    background-color: #28a745;
    color: #fff;
  }

  .badge-warning {
    background-color: #ffc107;
    color: #212529;
  }

  .badge-danger {
    background-color: #dc3545;
    color: #fff;
  }
	
  </style>
  