<script>
    import polimiDark from "$lib/assets/polimi-dark.png";
    import polimiLight from "$lib/assets/polimi-light.png";
</script>

<footer class="footer">
    <div class="logo-container">
        <picture>
            <source srcset={polimiDark} media="(prefers-color-scheme: dark)" />
            <img src={polimiLight} alt="Politecnico di Milano" />
        </picture>
    </div>
</footer>

<style>
    .footer {
        height: 110px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .logo-container {
        height: 78px;
        width: 201px;
    }

    img {
        width: 100%;
        height: 100%;
        object-fit: contain;
    }
</style>