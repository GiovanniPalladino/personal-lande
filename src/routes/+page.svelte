<script>

import Project from "$lib/components/Project.svelte";

    const filters = [
        { label: 'tutto', value: 'tutto' },
        { label: 'i miei pensieri', value: 'i miei pensieri' },
        { label: 'opere che amo', value: 'opere che amo' }
    ];

        const images = [
            { src: '/images/project/i miei pensieri/007.JPG', group: 'i miei pensieri', number: 'La folle genesi', year: 'Art. 1' },
            { src: '/images/project/i miei pensieri/008.JPG', group: 'i miei pensieri', number: 'Vita notturna milanese', year: 'Art. 2' },
            { src: '/images/project/i miei pensieri/009.JPG', group: 'i miei pensieri', number: 'Cosa si prova alle 13', year: 'Art. 3' },
            { src: '/images/project/i miei pensieri/010.JPG', group: 'i miei pensieri', number: 'Cadendo ho pensato questo', year: 'Art. 4' },
            { src: '/images/project/i miei pensieri/011.JPG', group: 'i miei pensieri', number: 'Segni del tempo', year: 'Art. 5' },
            { src: '/images/project/i miei pensieri/012.JPG', group: 'i miei pensieri', number: 'Natale in ospedale e Dostoevskij', year: 'Art. 6' },
            { src: '/images/project/opere che amo/001.jpg', group: 'opere che amo', number: 'PaaLabRes', year: 'J. Cage' },
            { src: '/images/project/opere che amo/002.jpg', group: 'opere che amo', number: 'Butterfly', year: 'S. Terayama' },
            { src: '/images/project/opere che amo/003.jpg', group: 'opere che amo', number: 'J O U R A F O', year: 'C. Andre' },
            { src: '/images/project/opere che amo/004.jpg', group: 'opere che amo', number: 'Paura nella città dei morti viventi', year: 'L. Fulci' },
            { src: '/images/project/opere che amo/005.jpg', group: 'opere che amo', number: '#2533', year: 'H. Finster' },
            { src: '/images/project/opere che amo/006.jpg', group: 'opere che amo', number: 'Blue Memory', year: 'G. Orozco' }
        ];

    let currentFilter = $state('tutto');

    let filteredImages = $derived.by(() => {
        if (currentFilter === 'tutto') return images;
        return images.filter(img => img.group === currentFilter);
    });
</script>

<section class="header">
    <p class="hero-text">
       Questo spazio nasce come una raccolta editoriale di pensieri e suggestioni attorno a temi molteplici e opere autoriali che ho amato. 
       <br>
       Tra parole e immagini prende forma un luogo dedicato all’esplorazione.
    </p>
    
</section>

<section class="desktop-page-content-filter">
    <div class="desktop-tab-navigation">
        <div class="tab-navigation">
            {#each filters as filter}
                <button
                    class="filter"
                    class:active={currentFilter === filter.value}
                    class:underline={filter.value === 'tutto' || filter.value === 'i miei pensieri' || filter.value === 'opere che amo'}
                    on:click={() => (currentFilter = filter.value)}
                >
                    <p class="filter-text">{filter.label}</p>
                </button>
            {/each}
        </div>
    </div>

   <div class="card-grid">
        {#each filteredImages as img}
            <Project 
                src={img.src} 
                number={img.number} 
                year={img.year} 
            />
        {/each}
    </div>
</section>

<style>
    .header {
        height: 590px;
        display: flex;
        align-items: center;
        padding: var(--spacing-11) var(--spacing-10);
    }

    .hero-text {
        font-family: var(--font-primary);
        font-weight: 700;
        font-size: 40px;
        line-height: normal;
        color: var(--color-content-primary);
        width: 100%;
        margin: 0;
        text-align: center;
    }

    .desktop-page-content-filter {
        display: flex;
        flex-direction: column;
        gap: var(--spacing-7);
    }

    .desktop-tab-navigation {
        height: 48px;
        position: relative;
    }

    .tab-navigation {
        display: flex;
        gap: var(--spacing-7);
        align-items: center;
        position: absolute;
        left: 0;
        top: 0;
        padding-left: var(--spacing-10);
        width: 100%;
    }

    .filter {
        background: none;
        border: none;
        padding: var(--spacing-2) var(--spacing-4);
        border-radius: var(--radius-full);
        cursor: pointer;
        font: inherit;
    }

    .filter-text {
        font-family: var(--font-secondary);
        font-size: 24px;
        color: var(--color-content-primary);
        margin: 0;
        transition: color 0.25s var(--ease-out-quart);
    }

    .filter.active {
        background: var(--color-filter-background-selected);
    }

    .filter.active .filter-text {
        color: var(--color-filter-content-selected);
    }

    /* Underline variant for specific filters: underline + link color when active */
    .filter.underline.active {
        background: none;
        border-radius: 0;
    }

    .filter.underline.active .filter-text {
        color: var(--color-link);
        text-decoration: underline;
        text-decoration-thickness: 2px;
        text-underline-offset: 6px;
    }

.card-grid {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 24px 24px;
        padding: 0 var(--spacing-10);
        align-items: stretch;
    }

    .text-content {
        display: flex;
        font-family: var(--font-primary);
        font-weight: 700;
        font-size: 24px;
        line-height: normal;
        gap: var(--spacing-2);
    }

    .primary {
        color: var(--color-content-primary);
    }

    .secondary {
        color: var(--color-content-secondary);
    }

    @media (max-width: 744px) {
        .header {
            height: auto;
            padding: var(--spacing-7) var(--spacing-5);
        }

        .hero-text {
            font-size: 24px;
            width: 100%;
            text-align: left;
        }

        .desktop-tab-navigation {
            height: auto;
        }

        .tab-navigation {
            position: static;
            width: 100%;
            padding: 0 var(--spacing-5);
            gap: var(--spacing-4);
            flex-wrap: wrap;
        }

        .filter {
            padding: var(--spacing-3) var(--spacing-4);
        }

        .filter-text {
            font-size: 20px;
        }

        .card-grid {
            grid-template-columns: 1fr;
            gap: var(--spacing-6);
            padding: 0 var(--spacing-5);
            justify-items: stretch;
        }
    }

    @media (max-width: 402px) {
        .header {
            padding: var(--spacing-5) var(--spacing-4);
        }

        .hero-text {
            font-size: 24px;
            text-align: center;
        }

        .tab-navigation {
            padding: 0 var(--spacing-4);
            gap: var(--spacing-3);
        }

        .filter {
            padding: var(--spacing-2) var(--spacing-3);
        }

        .filter-text {
            font-size: 18px;
        }

        .card-grid {
            gap: var(--spacing-5);
            padding: 0 var(--spacing-4);
        }
    }
</style>