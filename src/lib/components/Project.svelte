<script>
    import Icon from "./Icon.svelte";
    let { src, number, year } = $props();
</script>

<div class="card">
    <div class="img-container">
        <div class="veil"></div>
        <img {src} alt="Project image" />
    </div>

    <div class="text-row">
        <div class="text-content">
            <span class="primary">{number}</span>
            <span class="secondary">/ {year}</span>
        </div>
        
        <div class="icon-wrapper">
            <Icon name="arrow-up-right" />
        </div>
    </div>
</div>

<style>
    .card {
        display: flex;
        flex-direction: column;
        gap: var(--spacing-2);
        width: 100%;
        height: 100%;
        min-height: 0;
    }

    .img-container {
        position: relative;
        aspect-ratio: 664 / 400;
        overflow: hidden;
        flex: 1 1 auto;
        min-height: 0;
    }

    .veil {
        position: absolute;
        inset: 0;
        background-color: var(--color-link);
        mix-blend-mode: soft-light;
        opacity: 0;
        transition: opacity 0.4s ease;
    }

    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .text-row {
        display: flex;
        justify-content: space-between; 
        align-items: center;
        width: 100%;
    }

    .text-content {
        display: flex;
        gap: 8px;
        font-family: var(--font-primary);
        font-weight: 700;
        font-size: 24px;
    }

    .primary { color: var(--color-content-primary); }
    .secondary { color: var(--color-content-secondary); }

    .icon-wrapper {
        font-size: 24px; 
        color: var(--color-content-primary);
        opacity: 0;
        transform: translateY(10px); 
        transition: all 0.4s cubic-bezier(0.25, 1, 0.5, 1);
    }

    @media (max-width: 744px) {
        .card {
            display: flex;
            width: min(664px, 100%);
            flex-direction: column;
            align-items: flex-start;
            gap: var(--spacing-2, 8px);
        }

        .img-container {
            aspect-ratio: 664 / 400;
        }

        .text-content {
            gap: 6px;
            font-size: 20px;
        }

        .icon-wrapper {
            font-size: 20px;
        }
    }

    @media (max-width: 402px) {
        .card {
            width: 100%;
        }

        .img-container {
            aspect-ratio: 1 / 0.75;
        }

        .text-content {
            font-size: 18px;
        }

        .icon-wrapper {
            font-size: 18px;
        }
    }

    .card:hover .veil {
        opacity: 1;
    }

    .card:hover .icon-wrapper {
        opacity: 1;
        transform: translateY(0);
    }
</style>