<script>
    let username = '';
    let email = '';
    let password = '';
    let confirmPassword = '';
    let errorMessage = '';
    let successMessage = '';
  
    function onSubmit(event) {
      event.preventDefault();
      if (password !== confirmPassword) {
        errorMessage = 'Paroolid ei kattu!';
        successMessage = '';
      } else {
        successMessage = 'Registreerimine õnnestus!';
        errorMessage = '';
        username = '';
        email = '';
        password = '';
        confirmPassword = '';
      }
    }
  </script>
  
  <form on:submit|preventDefault={onSubmit} class="form">
    <h2>Angulari abil loodud registreerimisvorm</h2>
    <input type="text" placeholder="Kasutajanimi" bind:value={username} required />
    <input type="email" placeholder="E-post" bind:value={email} required />
    <input type="password" placeholder="Parool" bind:value={password} required />
    <input type="password" placeholder="Kinnita parool" bind:value={confirmPassword} required />
    
    <button type="submit">Registreeru</button>
  
    {#if errorMessage}
      <p class="error">{errorMessage}</p>
    {/if}
    {#if successMessage}
      <p class="success">{successMessage}</p>
    {/if}
  </form>
  
  <style>
    .form {
      background: white;
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      text-align: center;
      width: 300px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
  
    input {
      padding: 0.5rem;
      border: 1px solid #ccc;
      border-radius: 6px;
    }
  
    button {
      background: #405fac;
      color: white;
      border: none;
      padding: 0.7rem;
      border-radius: 6px;
      cursor: pointer;
      font-weight: bold;
    }
  
    .error {
      color: red;
      font-size: 0.9rem;
    }
  
    .success {
      color: green;
      font-size: 0.9rem;
    }
  </style>
  