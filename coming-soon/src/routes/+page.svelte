<script>
	import '../app.css';
	import { LazyBrush } from 'lazy-brush';
	import { scrollTo, scrollRef, scrollTop } from 'svelte-scrolling';
	import Icon from '@iconify/svelte';
	import { LoremIpsum } from 'lorem-ipsum';

	const lorem = new LoremIpsum({
		sentencesPerParagraph: {
			max: 8,
			min: 4
		},
		wordsPerSentence: {
			max: 16,
			min: 4
		}
	});

	const lazy = new LazyBrush({
		radius: -7,
		enabled: true,
		initialPoint: { x: 0, y: 0 }
	});

	let xPos = 0;
	let yPos = 0;
</script>

<svelte:window
	on:mousemove={(e) => {
		lazy.update({ x: e.clientX - 30, y: e.clientY - 30 }, { friction: 0.3 });
		({ x: xPos, y: yPos } = lazy.getBrushCoordinates());
	}}
/>

<div
	style="left: {xPos}px; top: {yPos}px"
	class="w-20 h-20 rounded-full bg-white mix-blend-difference fixed cursor-none z-50 pointer-events-none snap-align-none"
	role="presentation"
/>
<div class="snap-y snap-mandatory">
	<div
		class="w-screen h-screen bg-black justify-center items-center flex cursor-none snap-start"
		role="presentation"
	>
		<div
			class="absolute top-0 left-0 bg-transparent text-[7rem] text-white flex flex-col font-sans"
		>
			<div class="w-screen h-[50vh] bg-mesh10 bg-cover rounded-[3rem] font-extrabold">
				<div
					class="w-screen text-center text-black text-[10rem] bg-clip-text bg-cover bg-mesh5 z-40 tracking-widest mt-32"
				>
					TALLY
				</div>
				<div
					class="w-screen text-center text-black text-[1rem] bg-clip-text bg-cover bg-mesh2 z-40 tracking-[1.5rem]"
				>
					(coming soon)
				</div>
			</div>
		</div>

		<div
			class="w-screen h-[35vh] flex flex-row items-center justify-center space-x-9 py-10 mt-[30vh] cursor-none"
		>
			<div
				class="w-1/4 h-full bg-white rounded-[3rem] bg-mesh3 bg-cover transition hover:scale-105 cursor-none"
				use:scrollTo={'page1'}
			></div>
			<div
				class="w-1/4 h-full bg-white rounded-[3rem] bg-mesh4 bg-cover transition hover:scale-105 cursor-none"
				use:scrollTo={'page2'}
			></div>
			<div
				class="w-1/4 h-full bg-white rounded-[3rem] bg-mesh2 bg-cover transition hover:scale-105 cursor-none"
				use:scrollTo={'page3'}
			></div>
		</div>
	</div>
	<div class="w-screen absolute flex items-center justify-center bg-transparent bottom-[2vh]">
		<div
			class="w-[8rem] h-[5rem] hover:scale-125 active:scale-105 transition cursor-none flex items-center justify-center"
		>
			<Icon icon="ri:arrow-drop-down-fill" class="text-white w-20 h-20 " />
		</div>
	</div>

	<div
		class="w-screen h-screen bg-black text-white cursor-none snap-start"
		role="presentation"
		use:scrollRef={'page1'}
	>
		<div class="w-screen h-[55%] bg-transparent flex flex-row">
			<div
				class="w-full h-full text-[8rem] text-center flex items-center justify-center tracking-wider leading-none pl-10 bg-mesh11 text-black rounded-[3rem] bg-cover t font-extrabold"
			>
				PRODUCT SYNCING
			</div>
		</div>
		<div class="w-screen h-[45%] rounded-[3rem] p-10 flex items-center">
			<div
				class="w-full rounded-[3rem] bg-white bg-opacity-5 text-3xl font-semibold text-zinc-400 tracking-wider leading-[1.8] p-5 overflow-hidden flex"
			>
				<p>
					Tally is designed to simplify product information management. It automatically detects and
					adds new products to connected services, streamlining your product launch process. With
					Tally, you can say goodbye to the tedious task of manually updating product information
					across multiple platforms. Tally also ensures that any changes made to existing product
					titles, descriptions, or images are automatically updated across all your stores. This
					feature saves you time and effort, allowing you to focus on other important aspects of
					your business. With Tally, product information management becomes a seamless and efficient
					process.
				</p>
			</div>
		</div>
	</div>

	<div
		class="w-screen h-screen bg-black text-white cursor-none snap-start"
		role="presentation"
		use:scrollRef={'signup'}
	>
		signup
	</div>
</div>
