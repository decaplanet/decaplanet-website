<script>
	import '../lib/reset.css';
	import '../lib/fonts.css';
	import { base } from '$app/paths';
</script>

<svelte:head>
	<title>Deca</title>
	<meta name="theme-color" content="#5F90E0" />
	<meta name="description" content="Programming enthusiast with a Graphic Design background." />

	<meta property="og:type" content="website" />
	<meta property="og:title" content="Deca" />
	<meta
		property="og:description"
		content="Programming enthusiast with a Graphic Design background."
	/>
	<meta property="og:image" content="{base}/images/thumbnail.png" />
	<meta property="og:url" content="https://decaplanet.github.io/decaplanet-website/" />

	<meta name="twitter:title" content="Deca" />
	<meta
		name="twitter:description"
		content="Programming enthusiast with a Graphic Design background."
	/>
	<meta name="twitter:image" content="{base}/images/thumbnail.png" />
	<meta name="twitter:card" content="summary_large_image" />

	<link rel="apple-touch-icon" href="{base}/images/logo192.png" />
</svelte:head>
<slot />
<a rel="me" hidden href="https://mastodon.social/@decaplanet">Mastodon</a>
<a rel="me" hidden href="https://hachyderm.io/@decaplanet">Mastodon</a>
