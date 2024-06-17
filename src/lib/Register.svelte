<script>
    let email = '';
    let password = '';
    let confirmPassword = '';
  
    function handleRegister() {
      if (password !== confirmPassword) {
        alert("Passwords do not match");
        return;
      }
      console.log('Registering with', email, password);
      // Add your registration logic here (e.g., call an API endpoint)
    }
  </script>
  
  <svelte:head>
    <title>Register</title>
    <meta name="description" content="Register Page" />
  </svelte:head>
  
  <div class="register-form">
    <h2 ><b>Register</b></h2>
    <form on:submit|preventDefault={handleRegister}>
      <div class="form-group">
        <label for="email">Email:</label>
        <input type="email" id="email" bind:value={email} required />
      </div>
      <div class="form-group">
        <label for="password">Password:</label>
        <input type="password" id="password" bind:value={password} required />
      </div>
      <div class="form-group">
        <label for="confirm-password">Confirm Password:</label>
        <input type="password" id="confirm-password" bind:value={confirmPassword} required />
      </div>
      <button type="submit">Register</button>
    </form>
  </div>
  
  <style>
    .register-form {
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
  