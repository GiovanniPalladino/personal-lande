<script>
    import {website} from "$lib/state.svelte.js"
</script>

<h3>title editor</h3>

<input type="text" bind:value={website.title}>