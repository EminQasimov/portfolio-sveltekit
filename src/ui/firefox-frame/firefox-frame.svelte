<script>
	import {
		ArrowLeftIcon,
		ArrowRightIcon,
		CloseIcon,
		MenuIcon,
		RefreshIcon,
		StarIcon
	} from '../icons';

	export let tabbar;
	export let url;
	export let style = '';
	export let customClass = '';
	export let leftClickHandler = () => {};
	export let rightClickHandler = () => {};
	export let buttonEnter = () => {};
	export let buttonLeave = () => {};
	export let focusHandler = (e) => {};
</script>

<div class="FirefoxBrowserFrame" class:customClass {style}>
	{#if tabbar}
		<div class="tabbar">
			<div class="tab-buttons">
				<span />
				<span />
				<span />
			</div>
			<div class="tab" />
			<span class="close">
				<CloseIcon />
			</span>
			<div class="plus" />
		</div>
	{/if}

	<div class="searchbar">
		<div class="buttons" on:mouseenter={buttonEnter} on:mouseleave={buttonLeave}>
			<span on:click={leftClickHandler} class="left-button">
				<ArrowLeftIcon />
			</span>
			<span on:click={rightClickHandler} class="right-button">
				<ArrowRightIcon />
			</span>
			<span style="display: {tabbar ? 'none' : 'inline-block'}">
				<RefreshIcon />
			</span>
		</div>
		<div class="searchinput">
			<input
				spellCheck="false"
				type="text"
				value={url}
				on:click={(e) => {
					focusHandler(e.target.value);
				}}
			/>
			<span>
				<StarIcon />
			</span>
		</div>
		<div class="menuicon">
			<MenuIcon />
		</div>
	</div>

	<div class="content" style="height: {tabbar ? '' : '100%'}">
		<slot />
	</div>
</div>

<style lang="scss" src="./firefox-frame.scss" global></style>
