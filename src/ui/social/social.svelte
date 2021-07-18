<script lang="ts">
	import FacebookMobile from './facebook/facebook-mobile.svelte';
	import FirefoxBrowserFrame from '../firefox-frame/firefox-frame.svelte';
	import Canvas from './emoji-canvas/canvas.svelte';

	const PostData = [
		{
			video: 'https://www.facebook.com/emin.qasimovdia/videos/1267311960099492/',
			time: 'April 25, 2019'
		},
		{
			video: 'https://www.facebook.com/emin.qasimovdia/videos/1274803902683631/',
			time: 'May 6, 2019'
		},
		{
			video: 'https://www.facebook.com/emin.qasimovdia/videos/1268757439954944/',
			time: 'April 27, 2019'
		},
		{
			video: 'https://www.facebook.com/emin.qasimovdia/videos/1284780458352642/',
			time: 'May 21, 2019'
		}
	];
</script>

<section class="social bg" id="social">
	<div class="container">
		<p class="second_title">I am on</p>
		<h1 class="main_title">Facebook</h1>
		<div class="right">
			<FirefoxBrowserFrame
				url="facebook.com/emin.qasimovdia"
				customClass="customClass"
				tabbar={false}
				focusHandler={(url) => window.open('https://' + url, '_blank')}
			>
				<FacebookMobile data={PostData} />
			</FirefoxBrowserFrame>
		</div>
		<div class="left">
			<Canvas />
		</div>
	</div>
</section>

<style lang="scss" src="./social.scss" global>
</style>
