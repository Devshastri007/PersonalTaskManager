<script>
    import { goto } from "$app/navigation";

    let email = '';
    let password = '';
  
    function handleLogin() {
      console.log('Logging in with', email, password);
      // Add your login logic here (e.g., call an API endpoint)

      goto('/tasks/all');
    }
  </script>
  
  <svelte:head>
    <title>Login</title>
    <meta name="description" content="Login Page" />
  </svelte:head>
  
  <div class="login-form">
    <h2><b>Login</b></h2>
    <form on:submit|preventDefault={handleLogin}>
      <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" id="email" bind:value={email} required />
      </div>
      <div class="form-group">
        <label for="password">Password:</label>
        <input type="password" id="password" bind:value={password} required />
      </div>
      <button type="submit">Login</button>
    </form>
  </div>
  
  <style>
    .login-form {
      max-width: 400px;
      margin: auto;
      padding: 1em;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .form-group {
      margin-bottom: 1em;
    }
    label {
      display: block;
      margin-bottom: 0.5em;
    }
    input {
      width: 100%;
      padding: 0.5em;
      box-sizing: border-box;
    }
    button {
      padding: 0.5em 1em;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
    }
  </style>
  