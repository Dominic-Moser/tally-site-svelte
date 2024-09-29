<script>
	import '../app.css';
	import { LazyBrush } from 'lazy-brush';

	const lazy = new LazyBrush({
		radius: 5,
		enabled: true,
		initialPoint: { x: 0, y: 0 }
	});

	let xPos = 0;
	let yPos = 0;
</script>

<div
	style="left: {xPos}px; top: {yPos}px"
	class="w-10 h-10 rounded-full bg-white mix-blend-difference absolute cursor-none"
	role="presentation"
></div>

<div
	class="w-screen h-screen bg-black cursor-none justify-center items-center flex"
	on:mousemove={(e) => {
		lazy.update({ x: e.clientX, y: e.clientY }, { friction: 0.3 });
		({ x: xPos, y: yPos } = lazy.getBrushCoordinates());
	}}
	role="presentation"
>
	<div class="w-52 h-52 bg-white">lalal</div>
</div>
