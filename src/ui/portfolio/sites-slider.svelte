<script lang="ts">
	import Frame from './frame.svelte';

	export let framesData = [];
	export let activeIndex = 0;
</script>

<div class="iframes">
	{#each framesData as frame, index}
		{#if activeIndex === index}
			<div class="frame-wrapper">
				<Frame {...frame} />
			</div>
		{/if}
	{/each}
</div>

<style>
	.iframes {
		position: relative;
		width: 100%;
		height: 100%;
	}

	.frame-wrapper {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
	}
</style>
