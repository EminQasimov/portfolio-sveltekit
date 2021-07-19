<script>
	export let url = '';
	export let title = '';

	let loading = true;
</script>

<div class="frame">
	{#if loading}
		<div class="spinner" />
	{/if}

	<iframe
		class="myTarget"
		src={url}
		frameBorder="0"
		{title}
		style="display: {loading ? 'none' : 'inline-block'}"
		on:load={() => (loading = false)}
	/>
</div>

<style>
	.myTarget {
		width: 100%;
		height: 100%;
	}
	.frame {
		width: 100%;
		height: 100%;
		display: flex;
		align-items: center;
		justify-content: center;
		overflow: hidden;
	}
</style>
