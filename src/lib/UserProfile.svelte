<script>

import userIcon from '$lib/images/user-icon.jpg'; 
	export let user = {
	  name: 'John Doe',
	  email: 'john.doe@example.com',
	  bio: 'John Doe is a gentleman',
	};
  </script>
  
  <div class="user-profile card">
	<img src={userIcon} alt="Profile Picture" class="card-img-top" />
	<div class="card-body">
	  <h5 class="card-title">Name --- {user.name}</h5>
	  <p class="card-text">Email -- {user.email}</p>
	  <p class="card-text">About -- {user.bio}</p>
	</div>
  </div>
  
  <style>
	.user-profile {
	  width: 18rem;
	  margin: 1rem auto;
	}
	.card-img-top {
	  border-radius: 50%;
	  width: 150px;
	  height: 150px;
	  margin: 1rem auto;
	  display: block;
	}
	.card-title {
	  text-align: center;
	  margin-top: 1rem;
	}
	.card-text {
	  text-align: center;
	}
  </style>
  