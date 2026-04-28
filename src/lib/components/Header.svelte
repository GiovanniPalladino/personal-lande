<script>
    import Link from "$lib/components/Link.svelte";
</script>

<header class="top-bar">
    <div class="link">
        <Link title="Pensieri" ref="/" />
    </div>

    <div class="content-right">
        <div class="link">
            <Link title="about" ref="/" />
        </div>
        <div class="link">
            <Link
            title="Instagram @28.72491"
            ref="https://www.instagram.com/28.72491"
            />
        </div>
    </div>
</header>

<style>
    .top-bar {
        height: 86px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        padding: var(--spacing-6) var(--spacing-10);
    }

    .link {
        font-family: var(--font-secondary);
        font-size: 24px;
        line-height: 22px;
        color: var(--color-content-primary);
        text-decoration: none;
    }

    .content-right {
        display: flex;
        gap: var(--spacing-6);
        align-items: center;
    }

    @media (max-width: 744px) {
        .top-bar {
            padding: var(--spacing-5) var(--spacing-6);
        }

        .link {
            font-size: 20px;
        }

        .content-right {
            gap: var(--spacing-4);
        }
    }

    @media (max-width: 402px) {
        .top-bar {
            padding: var(--spacing-5) var(--spacing-4);
        }

        .link {
            font-size: 18px;
        }

        .content-right {
            gap: var(--spacing-3);
        }
    }
</style>