<script>
	import { DotsHorizontalIcon } from '../../icons';
	import { onMount } from 'svelte';

	export let postDate;
	export let video;

	let fbVideo;
	let isloading = true;
	let windowWidth = 1200;

	onMount(() => {
		// windowWidth = window?.innerWidth;

		let inter = setInterval(() => {
			let elem = fbVideo.getAttribute('fb-xfbml-state');
			if (elem === 'rendered') {
				isloading = false;
				clearInterval(inter);
			}
		}, 3000);
	});
</script>

<div class="facebook-post">
	<div class="post-head">
		<span />
		<div class="author">
			<div class="name">
				<a href="https://facebook.com/emin.qasimovdia">Emin Qasimov</a>
				<p>
					shared a video to the group:
					<a href="https://www.facebook.com/groups/frontenddevelopersazerbaijan">
						Frontend Developers - Azerbaijan
					</a>
					.
				</p>
			</div>
			<div class="time">{postDate}</div>
		</div>
		<div class="dots">
			<DotsHorizontalIcon />
		</div>
	</div>
	<div class={'post-body' + (isloading ? ' preloader' : '')}>
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
