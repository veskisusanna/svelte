<script>
  let count = 0;

  function increment() {
    count += 1;
  }
</script>

<div class="counter-card">
  <h2>Loenduri väärtus: {count}</h2>
  <button on:click={increment}>Loendur</button>
</div>

<style>
  .counter-card {
    background-color: #fff;
    padding: 2rem;
    border-radius: 12px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    text-align: center;
    min-width: 280px;
    margin-top: 2rem;
  }

  h2 {
    margin-bottom: 1.5rem;
    font-size: 1.8rem;
  }

  button {
    background-color: #2563eb;
    color: #fff;
    border: none;
    border-radius: 8px;
    padding: 0.6rem 1.5rem;
    font-size: 1.1rem;
    cursor: pointer;
  }

  button:hover {
    background-color: #1d4ed8;
  }
</style>
