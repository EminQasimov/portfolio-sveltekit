<script>
	import {
		ArrowLeftIcon,
		ArrowRightIcon,
		CloseIcon,
		MenuIcon,
		RefreshIcon,
		StarIcon
	} from '../icons';

	export let tabbar,
		url,
		customClass,
		leftClickHandler = () => {},
		rightClickHandler = () => {},
		buttonEnter = () => {},
		buttonLeave = () => {},
		focusHandler = (e) => {};
</script>

<div class="FirefoxBrowserFrame" class:customClass>
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
			<span onClick={leftClickHandler} class="left-button">
				<ArrowLeftIcon />
			</span>
			<span onClick={rightClickHandler} class="right-button">
				<ArrowRightIcon />
			</span>
			<span style="display: ${tabbar ? 'none' : 'inline-block'} ">
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

	<div class="content" style="height: ${tabbar ? '' : '100%'}">
		<slot />
	</div>
</div>

<style lang="scss" src="./firefox-frame.scss" global></style>
