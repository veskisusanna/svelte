<script>
    let isRunning = false;
    let time = 0;
    let finalTime = null;
    let startTime;
    let intervalId;
  
    function startStop() {
      if (!isRunning) {
        isRunning = true;
        finalTime = null;
        startTime = performance.now();
  
        intervalId = setInterval(() => {
          time = (performance.now() - startTime) / 1000;
        }, 50);
      } else {
        isRunning = false;
        clearInterval(intervalId);
        finalTime = time;
      }
    }
  </script>
  
  <div class:running={isRunning} class="stopper-card">
    <h2>Svelte proovileht</h2>
    <p class="subtext">Lõputöö raames interaktiivne nupp Sveltes.</p>
  
    <button on:click={startStop}>
      {isRunning ? 'Stop' : 'Start'}
    </button>
  
    {#if isRunning}
      <p class="live-time">Aeg: {time.toFixed(3)}s</p>
    {/if}
  
    {#if finalTime !== null}
      <p class="final-time">Lõpuaeg: {finalTime.toFixed(3)}s</p>
    {/if}
  </div>
  
  <style>
    .stopper-card {
      background-color: #fff;
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      text-align: center;
      min-width: 280px;
      transition: background-color 0.3s ease, color 0.3s ease;
    }
  
    .stopper-card.running {
      background-color: red;
      color: white;
    }
  
    h2 {
      margin: 0 0 0.5rem 0;
    }
  
    .subtext {
      margin-bottom: 1.5rem;
      font-size: 0.95rem;
    }
  
    button {
      padding: 0.5rem 1.2rem;
      font-size: 1rem;
      background-color: #007bff;
      border: none;
      color: white;
      border-radius: 6px;
      cursor: pointer;
      margin: 0.5rem 0;
    }
  
    button:hover {
      background-color: #0056b3;
    }
  
    .live-time, .final-time {
      font-size: 1rem;
      margin-top: 0.5rem;
    }
  </style>
  