<script>
	import { DotsHorizontalIcon } from '../../icons';
	import { onMount } from 'svelte';

	export let postDate;
	export let video;

	let fbVideo;
	let isloading = true;
	let error = false;
	let windowWidth = 1200;
	let checkingDuration = 0;

	onMount(() => {
		windowWidth = window?.innerWidth;

		let timeout;

		function checkFacebookPostsLoaded() {
			let elem = fbVideo?.getAttribute('fb-xfbml-state');
			// check it for 2 minutes
			if (elem === 'rendered' || checkingDuration > 1000 * 120) {
				isloading = false;
				error = true;
				clearTimeout(timeout);
			} else {
				checkingDuration += 100;
				timeout = setTimeout(checkFacebookPostsLoaded, 100);
			}
		}

		checkFacebookPostsLoaded();
	});
</script>

<div class="facebook-post">
	<div class="post-head">
		<!-- <span /> repeated avatar -->
		<div class="author">
			<div class="name">
				<a href="https://facebook.com/emin.qasimovdia">Emin Qasimov</a>
				<p>
					shared a video to the group:
					<a href={video}> Frontend Developers - Azerbaijan </a>
				</p>
			</div>
			<div class="time">{postDate}</div>
		</div>
		<div class="dots">
			<DotsHorizontalIcon />
		</div>
	</div>
	<div class={'post-body' + (isloading ? ' preloader' : '')}>
		{#if error}
			<div class="error-video-link">
				<a href={video}>
					<p>View on Facebook.com</p>
					<p>
						{video}
					</p>
				</a>
			</div>
		{/if}

		<div
			class="fb-video"
			bind:this={fbVideo}
			data-href={video}
			data-show-text="true"
			data-width={windowWidth >= 600 ? 'auto' : 350}
			data-autoplay="false"
		/>
	</div>
</div>
