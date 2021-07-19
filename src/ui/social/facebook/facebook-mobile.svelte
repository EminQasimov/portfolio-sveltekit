<script lang="ts">
	import Post from './post.svelte';
	import { FacebookIcon, GearIcon, ImageIcon, SearchIcon } from '../../icons';

	export let data = [];
</script>

<div id="facebook">
	<header>
		<div class="logo-search">
			<span class="logo">
				<FacebookIcon />
			</span>
			<label class="search-wrapper">
				<span class="search-icon">
					<SearchIcon />
				</span>
				<input type="text" placeholder="Search" class="search" />
			</label>
		</div>
		<div class="setting">
			<span>
				<GearIcon />
			</span>
		</div>
	</header>
	<div class="fb-middle">
		<div class="story-wrapper">
			<h1>Stories</h1>
			<ul class="stories">
				<li class="story" />
				<li class="story" />
				<li class="story" />
				<li class="story" />
				<li class="story" />
				<li class="story" />
				<li class="story" />
				<li class="story" />
			</ul>
		</div>
		<div class="fb-send">
			<div class="post-profile" />
			<div class="send-input">Add a post</div>
			<div class="send-button">
				<ImageIcon />
			</div>
		</div>

		<div class="fb-posts">
			{#each data as { video, time }}
				<Post {video} postDate={time} />
			{/each}
		</div>
	</div>
</div>

<style lang="scss" src="./facebook-mobile.scss" global></style>
