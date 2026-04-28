<script>
    const { name, variant = "regular" } = $props();
    const pack = variant === "fill" ? "ph-fill" : "ph";
</script>

<svelte:head>
    <link 
    rel="stylesheet" 
    type="text/css"
    href="http://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.1/src/regular/style.css"
/>

    <link
    rel="stylesheet"
    type="text/css"
    href="http://cdn.jsdelivr.net/npm/@phosphor-icons/web@2.1.1/src/fill/style.css"
    />
</svelte:head>

<i class={`${pack} ph-${name}`}></i>