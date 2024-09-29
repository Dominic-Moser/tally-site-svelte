<script>
	import '../app.css';
	let something = 'help';
	let count = 1;

	let testVar = 10;
</script>

<div class="w-screen h-min bg-black">
	<div class="h-screen w-screen bg-black flex gap-4 p-4">
		<div
			class="w-[6vw] h-full bg-zinc-50 rounded-[1.5rem] flex flex-col items-center justify-center"
		>
			<div
				class="w-[100%] h-1/2 bg-transparent flex flex-col items-center justify-center p-1 gap-10"
			>
				{#each new Array(3) as page}
					<div
						class="w-[100%] h-[10vh] bg-black text-white rounded-3xl hover:scale-105 transition-transform"
					></div>
				{/each}
			</div>
		</div>
		<div
			class="w-[92vw] h-full bg-transparent p-1 flex-col items-center justify-center space-y-4 overflow-auto scroll-0 scroll-smooth scrollbar-hide"
		>
			<div class="max-w-full bg-transparent h-[90vh] rounded-3xl flex-col shadow-gray-400">
				<div class="h-3/5 w-full bg-white rounded-t-[1.5rem]"></div>
				<div class="h-2/5 bg-transparent flex overflow-auto space-x-2 pt-2">
					{#each new Array(2) as s}
						<div class="w-1/2 bg-white rounded-b-[1.5rem]"></div>
					{/each}
				</div>
			</div>
			<div class="max-w-full bg-white h-[90vh] rounded-3xl flex-col shadow-gray-400"></div>
			<div class="max-w-full bg-white h-[90vh] rounded-3xl flex-col shadow-gray-400"></div>
		</div>
	</div>
</div>
