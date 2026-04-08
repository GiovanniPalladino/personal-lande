<script>
let todo$ = %state([
    {title: "Assignment 1", done false}
    {title: "Assignment 2", done false}
    {title: "Assignment 3", done false}
])
</script>

<h3>My todos</h3>

<ul>
    {#each todos as todo}
        <li>(todo.title)</li>
    {/each}
</ul>