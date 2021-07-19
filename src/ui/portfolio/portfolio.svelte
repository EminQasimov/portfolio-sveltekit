<script>
	import FirefoxBrowserFrame from '../firefox-frame/firefox-frame.svelte';
	import SitesSlider from './sites-slider.svelte';

	const framesData = [
		{
			url: 'https://eminqasimov.github.io/loginsignupform',
			title: 'Login and Sign up Form UI animation'
		},
		{
			url: 'https://eminqasimov.github.io/colorui',
			title: 'Color UI Landing Page'
		},
		{
			url: 'https://eminqasimov.github.io/hospital-dashboard-with-antdui',
			title: 'Hospital dashboard UI with Ant Design UI kit'
		},
		{
			url: 'https://eminqasimov.github.io/3d-box-css',
			title: 'Opening 3D cardboard Box Animation'
		},
		{
			url: 'https://eminqasimov.github.io/3dCarAnimation',
			title: '3D Car Animation'
		},
		{
			url: 'https://eminqasimov.github.io/flag-animation/',
			title: 'Interactive Flag Animation '
		},
		{
			url: 'https://eminqasimov.github.io/app.prospect.az-logo-preloder/',
			title: 'Prospect.az logo animation preloader '
		},
		{
			url: 'https://eminqasimov.github.io/striped-background',
			title: 'Striped Background Effect With CSS'
		},
		{
			url: 'https://eminqasimov.github.io/pure-css-photo-collage',
			title: 'Responsive Pure CSS Photo Collage'
		},
		{
			url: 'https://codepen.io/eminqasimov/full/yrzZwJ',
			title: 'mask login ui'
		},
		{
			url: 'https://codepen.io/eminqasimov/full/eamvrQ',
			title: 'Pie Image Carousel'
		},
		{
			url: 'https://player.vimeo.com/video/343181095?loop=1',
			title: 'Rolling Movies Carousel'
		},
		{
			url: 'https://player.vimeo.com/video/343177258?loop=1',
			title: 'new Facebook Design'
		}
	];

	let activeIndex = 0;
	$: activeUrl = framesData[activeIndex].url;

	function prev() {
		if (activeIndex > 0) {
			activeIndex--;
		} else {
			activeIndex = framesData.length - 1;
		}
	}

	function next() {
		if (activeIndex < framesData.length - 1) {
			activeIndex++;
		} else {
			activeIndex = 0;
		}
	}

	const focusHandler = (href = 'https://eminqasimov.github.io') => {
		window.open(href, '_blank');
	};
</script>

<section class="portfolio" id="portfolio">
	<div class="container">
		<p>My</p>
		<h1>Portfolio</h1>
		<FirefoxBrowserFrame
			style="width: 100%; height: 89%; position: relative; left: 0"
			tabbar={true}
			url={activeUrl}
			leftClickHandler={prev}
			rightClickHandler={next}
			{focusHandler}
		>
			<SitesSlider {activeIndex} {framesData} />
		</FirefoxBrowserFrame>
	</div>
</section>

<style lang="scss" src="./portfolio.scss" global>
</style>
