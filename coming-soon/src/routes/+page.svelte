<script>
	import '../app.css';
	import { LazyBrush } from 'lazy-brush';

	const lazy = new LazyBrush({
		radius: -7,
		enabled: true,
		initialPoint: { x: 0, y: 0 }
	});

	let xPos = 0;
	let yPos = 0;
</script>

<div
	style="left: {xPos}px; top: {yPos}px"
	class="w-10 h-10 rounded-full bg-white mix-blend-difference absolute cursor-none z-50"
	role="presentation"
	on:mousemove={(e) => {
		lazy.update({ x: e.clientX - 15, y: e.clientY - 15 }, { friction: 0.3 });
		({ x: xPos, y: yPos } = lazy.getBrushCoordinates());
	}}
></div>

<div
	class="w-screen h-screen bg-black justify-center items-center flex cursor-none"
	on:mousemove={(e) => {
		lazy.update({ x: e.clientX - 15, y: e.clientY - 15 }, { friction: 0.3 });
		({ x: xPos, y: yPos } = lazy.getBrushCoordinates());
	}}
	role="presentation"
>
	<div class="absolute top-0 left-0 bg-transparent text-[7rem] text-white flex flex-col font-sans">
		<div
			class="w-screen text-center text-transparent text-[10rem] bg-clip-text bg-cover bg-mesh5 z-40 tracking-widest mt-32"
		>
			TALLY
		</div>
		<div
			class="w-screen text-center text-transparent text-[1rem] bg-clip-text bg-cover bg-mesh5 z-40 tracking-widest"
		>
			(coming soon)
		</div>
	</div>

	<div
		class="w-screen h-[35vh] flex flex-row items-center justify-center space-x-5 py-10 mt-[30vh]"
	>
		<div class="w-1/4 h-full bg-white rounded-[3rem] bg-mesh4 bg-cover transition"></div>
		<div class="w-1/4 h-full bg-white rounded-[3rem] bg-mesh2 bg-cover transition"></div>
		<div class="w-1/4 h-full bg-white rounded-[3rem] bg-mesh3 bg-cover transition"></div>
	</div>
</div>
