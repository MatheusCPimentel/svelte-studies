<script>
	import TaskForm from './AddTaskForm.svelte';

	let tasks = [
		{ name: 'First task', id: 1, },
		{ name: 'Secound task', id: 2, },
		{ name: 'Third task', id: 3, },
		{ name: 'Fourth task', id: 4, },
	];

	const addTask = (e) => {
		const newTask = e.detail; // Está o objeto que foi "despachado" no outro arquivo
		tasks = [newTask, ...tasks] // "tasks" recebe a nova Task + as tasks que já existiam
	}

	const handleClick = (id) => {
		tasks = tasks.filter((task) => task.id != id )
	}

</script>

<TaskForm on:addTask={addTask} />

<main>
	{#each tasks as task(task.id)}
		<div>
			<h4>{task.name}</h4>
			<button on:click={() => {handleClick(task.id)}}>Delete!</button>
		</div>
	{:else}
		 <p>There're no tasks to show...</p>
	{/each}
</main>

<style>
	main {
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>