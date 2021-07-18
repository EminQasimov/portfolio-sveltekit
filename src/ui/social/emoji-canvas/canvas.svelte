<script lang="ts">
	import initRequestAnimationFrame from '../../../utils/requestAnimationFrame';
	import { getMousePos, isNotMobile } from '../../../utils/functions';
	import Emoji from './emoji';
	import { onMount } from 'svelte';

	let inter, X, Y, canvasRef;

	onMount(() => {
		initRequestAnimationFrame();

		function resizeCanvas() {
			const canvas = canvasRef,
				w = canvas.offsetWidth,
				h = canvas.offsetHeight;
			canvas.width = w;
			canvas.height = h;
			if (isNotMobile() && Emoji.isFirst) {
				Emoji.generate(canvas);
			}
			Emoji.exist && Emoji.handleResize(w, h);
		}
		resizeCanvas();
		window.addEventListener('resize', resizeCanvas);

		return () => {
			window.removeEventListener('resize', resizeCanvas);
		};
	});

	const handleMouseMove = (e) => {
		if (isNotMobile() && Emoji.exist) {
			let { x, y } = getMousePos(canvasRef, e);
			X = x;
			Y = y;

			Emoji.add(X, Y);
		}
	};
</script>

<canvas
	bind:this={canvasRef}
	on:mousemove={(e) => handleMouseMove(e)}
	on:mouseleave={() => {
		clearInterval(inter);
	}}
>
	Please use Chrome for the best experience
</canvas>
