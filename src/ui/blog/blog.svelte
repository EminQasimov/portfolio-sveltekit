<script>
	import Card from './card.svelte';

	// imgs urls
	const oopjs = '/assets/oopjs-min.jpg';
	const reactfirebase = '/assets/reactfirebase-min.png';
	const es8 = '/assets/es8-min.png';
	const antipattern = '/assets/antipattern.jpeg';
	const fp = '/assets/fp.png';

	const data = [
		{
			img: es8,
			title: 'ES2017 (ES8) ilə Javascript-ə gələn yeniliklər nələrdir?',
			date: 'Jun 19',
			link: '/es2017-es8-ilə-javascript-ə-gələn-yeniliklər-nələrdir-a8b58c5cf52f'
		},
		{
			img: reactfirebase,
			title: 'React app-ı Firebase-ə necə yükləmək (deploy) olar? ',
			date: 'Jun 18',
			link: '/react-js-app-ı-firebase-ə-yükləmək-deploy-cc32d173d6fa'
		},

		{
			img: antipattern,
			title: 'React.js -də etdiyimiz səhvlər — Anti-pattern-lər',
			date: 'Jun 20',
			link: '/react-js-də-etdiyimiz-səhvlər-anti-pattern-lər-fb9eabe5c2a0'
		},
		{
			img: oopjs,
			title: 'Javascript-də OOP prinsipləri',
			date: 'Jun 17',
			link: '/javascript-də-oop-prinsipləri-5d4484a8a981'
		},
		{
			img: fp,
			title: 'Javascript-də Funksional Proqramlama',
			date: 'Jun 23',
			link: '/javascript-də-funksional-proqramlama-12adccc43f66'
		}
	];
</script>

<section id="blog" class="blog">
	<div class="container">
		<p>I am on</p>
		<h1>Medium</h1>
		<div class="articles">
			{#each data as post}
				<Card {post} />
			{/each}
			<div class="card fixflex" />
			<div class="card fixflex" />
			<div class="card fixflex" />
			<div class="card fixflex" />
			<div class="card fixflex" />
			<div class="card fixflex" />
		</div>
	</div>
</section>

<style lang="scss" src="./blog.scss" global></style>
