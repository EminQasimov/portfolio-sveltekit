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
	import Portfolio from '../ui/portfolio/portfolio.svelte';
	import Skills from '../ui/skills/skills.svelte';
	import Contact from '..//ui/contact/contact.svelte';

	import { onMount } from 'svelte';

	const getNarrowAndTall = () => {
		return window.innerWidth < 1024 || window.innerHeight > 1024;
	};

	let isNarrowAndTall = false;

	onMount(() => {
		window.addEventListener('resize', () => {
			isNarrowAndTall = getNarrowAndTall();
		});
	});
</script>

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

	<div class="sticky" style="z-index: {isNarrowAndTall ? 999 : 1}">
		<Portfolio />
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

<style lang="scss" global>
	@import '../styles/index.scss';
	@import '../styles/media-queries.scss';
	@import '../styles/spinner.scss';
</style>
