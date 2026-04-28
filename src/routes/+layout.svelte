<script>
	import favicon from '$lib/assets/favicon.svg';

import "$lib/styles/reset.css"
import "$lib/styles/tokens.css"
import "$lib/styles/tokens/colors.css"
import "$lib/styles/tokens/sizes.css" 
import "$lib/styles/base.css"
import "$lib/styles/utilities.css"

import Header from "$lib/components/Header.svelte"
import Footer from "$lib/components/Footer.svelte"

	const { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />

	<!-- thin -->
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://api.fontshare.com/v2/css?f[]=satoshi@300&display=swap" rel="stylesheet">


	<!-- bold -->
	<link rel="preconnect" href="https://fonts.googleapis.com">
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
	<link href="https://api.fontshare.com/v2/css?f[]=satoshi@900&display=swap" rel="stylesheet">
</svelte:head>

<Header />

{@render children()}

<Footer />
