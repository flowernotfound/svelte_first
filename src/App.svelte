<script>
  import Todo from './todo.svelte';
  
  let todos = [
    { text: 'Learn Svelte', done: false },
    { text: 'Build a Todo App', done: false }
  ];
  let newTodo = '';

  function addTodo() {
    todos = [...todos, { text: newTodo, done: false }];
    newTodo = '';
  }
  function removeTodo(index) {
    todos.splice(index, 1);
    todos = [...todos];
  }
	
</script>

<main>
  <h1>My Todo List</h1>
  <ul>
    {#each todos as todo}
      <li><Todo todo={todo} /></li>
    {/each}
  </ul>
  <input type="text" bind:value={newTodo} placeholder="New Todo" />
<button on:click={addTodo}>Add</button>
<ul>
  {#each todos as todo, index}
    <li>
      <Todo todo={todo} />
      <button on:click={() => removeTodo(index)}>Remove</button>
    </li>
  {/each}
</ul>
</main>
