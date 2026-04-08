<script>
import { onMount } from "svelte"

    let size = $state(50)
    let color = $state("#ffe00")

    let canvas

    onMount(() => {

    const context = canvas.getContext("2d")
    context.clearRect(0, 0, canvas.width, canvas.height)

    context.fillStyle = color
    context.fillRect(0, 0, size, size)
    })

</script>

<h3>canvas square</h3>

<article>
    <canvas width="100" height="100"></canvas>

    <nav>
        <label>
            Size: <input type="range">
        </label>

                <label>
            Color: <input type="color">
        </label>
    </nav>
</article>

<style>
    article { 
        display: flex;
        gap: 1em;
        align-items: end;
     }

      canvas { 
        border: solid 1px black;
     }

      article { 
        display: flex;
        gap: 1em;
        flex-direction: column;
     }
</style> 