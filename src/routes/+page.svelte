<script>
import { website } from "$lib/state.svelte"

    import CanvasSquare from "$lib/components/CanvasSquare.svelte";
    import ClicksCounter from "$lib/components/ClicksCounter.svelte"
    import TitleEditor from "$lib/components/TitleEditor.svelte";
    import TodoList from "$lib/components/TodoList.svelte";
    let count = $state(5)
</script>


<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>

<TitleEditor/>

<ClicksCounter bind:initialCount={count}/>

{#if count > 10 && count < 20}
<p>count from parent is {count} </p>
{:else if count > 30}
<p>that's a lot to click </p>
{:else}
<p>count is not in range </p>
{/if}
<CanvasSquare />

<TodoList/>

<style>
    h1 {
        color: deepskyblue;
    }
</style>