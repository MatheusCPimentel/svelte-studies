<script>
  import { createEventDispatcher } from 'svelte';

  let dispatch = createEventDispatcher();

  let name;

  const handleSubmit = () => {
    const tasks = {
      name,
      id: Math.random()
    };
    dispatch('addTask', tasks);
  };
</script>

<form on:submit|preventDefault={handleSubmit}>
  <h4>You can add new tasks here!</h4>
  <input type="text" placeholder="Add a new task here..." bind:value={name}>
  <button>Add task</button>
</form>

<style>

</style>