<script>
  export let todo;
</script>

<div>
  <input type="checkbox" bind:checked={todo.done} />
  <span>{todo.text}</span>
</div>
