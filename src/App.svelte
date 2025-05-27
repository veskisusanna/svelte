<script>
  import Counter from './lib/Counter.svelte';
  import Stopper from './lib/Stopper.svelte';
  import RegisterForm from './lib/RegisterForm.svelte';
</script>

<main>
  
    <RegisterForm/>
  

  <!-- <div>
    <Stopper />
  </div> -->
</main>
<style>
  main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  gap: 2rem;
  background-color: #f4f4f4;
}

.card {
  background-color: white;
  padding: 1.5rem; /* veidi väiksem padding */
  border-radius: 12px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  text-align: center;
  min-width: 250px; /* väiksem miinimilaius */
  max-width: 300px; /* maksimaalne laius */
}

</style>

