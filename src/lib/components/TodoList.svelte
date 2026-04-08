<script>
    let todos = $state([
        {title: "assignment 1", done: false},
        {title: "assignment 2", done: false},
        {title: "assignment 3", done: false},
    ])
</script>

<h3>my todos</h3>

<ul>
    {#each todos as todo}
        <li>
            <input type="checkbox" bind:checked={todo.done}>
            {todo.title}
        </li>
    {/each}
</ul>