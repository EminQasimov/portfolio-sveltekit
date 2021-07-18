<script context="module">
	// If hydrate and router are both false, SvelteKit will not add any JavaScript to the page at all.
	// export const hydrate = false;
	export const router = false;

	// export const prerender = true;
</script>

<script>
	import Social from '../ui/social/social.svelte';
	import Intro from '../ui/intro/intro.svelte';
	import Blog from '../ui/blog/blog.svelte';
	import Skills from '../ui/skills/skills.svelte';
	import Contact from '..//ui/contact/contact.svelte';

	import { onMount } from 'svelte';

	const title = "Emin Qasimov's Personal Website";
	const description = 'Emin Qasimov - Frontend Developer, view my portfolio and cv';
	const image = 'https://eminqasimov.xyz/eminqasimovfrontenddev.png';

	const getNarrowAndTall = () => {
		if (window.innerWidth < 1024 || window.innerHeight > 1024) {
			return true;
		} else {
			return false;
		}
	};

	let isNarrowAndTall = false;

	onMount(() => {
		window.addEventListener('resize', () => {
			isNarrowAndTall = getNarrowAndTall();
		});
	});
</script>

<svelte:head>
	<meta charset="utf-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1" />
	<link rel="shortcut icon" href="/favicon.ico" />
	<meta name="theme-color" content="#000000" />

	<meta name="image" content="https://eminqasimov.xyz/eminqasimovfrontenddev.png" />
	<meta itemprop="name" content="Emin Qasimov's Personal Website" />
	<meta
		itemprop="description"
		content="Emin Qasimov - Frontend Developer, view my portfolio and cv"
	/>
	<meta itemprop="image" content="https://eminqasimov.xyz/eminqasimovfrontenddev.png" />

	<meta property="og:title" content="Emin Qasimov's Personal Website" />
	<meta property="og:site_name" content="Emin Qasimov's Personal Website" />
	<meta property="og:url" content="https://eminqasimov.xyz" />
	<meta
		property="og:description"
		content="Emin Qasimov - Frontend Developer, view my portfolio and cv"
	/>
	<meta property="og:type" content="website" />
	<meta property="og:image" content="https://eminqasimov.xyz/eminqasimovfrontenddev.png" />
	<meta property="og:image" content="https://eminqasimov.xyz/emin.jpg" />

	<!-- <link rel="manifest" href="%PUBLIC_URL%/manifest.json" /> -->

	<link rel="preload" href="/assets/halfface.webp" as="image" />
	<link rel="preload" href="/assets/emojis.mp4" as="video" />
	<link rel="dns-prefetch" href="https://eminqasimov.github.io" />
	<link rel="dns-prefetch" href="https://connect.facebook.net" />
	<link
		href="https://fonts.googleapis.com/css?family=Montserrat:400,700&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<main class="main-wrapper dance">
	<div class="sticky">
		<Intro />
	</div>

	<div class="sticky" style="z-index: {isNarrowAndTall ? 999 : 1}">
		<Social />
	</div>

	<div class="sticky" style="z-index: 0; pointer-events: none">
		<section class="stuck" />
	</div>

	<div class="sticky">
		<Blog />
	</div>

	<div class="sticky" style="z-index: 0; pointer-events: none">
		<section class="stuck" />
	</div>

	<div class="sticky">
		<Skills />
	</div>

	<div class="sticky" style="z-index: 0; pointer-events: none">
		<section class="stuck" />
	</div>

	<div class="sticky">
		<Contact />
	</div>
</main>

<style lang="scss" src="../global.scss" global>
</style>
