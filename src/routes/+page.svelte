<script lang="ts">
	import { onMount } from 'svelte';

	let title = 'ZETA BETA TAU';
	let display = 'Z';

	const type = (text: string, i: number) => {
		const interval = setTimeout(() => {
			display = text.slice(0, i);
			if (i < text.length) {
				type(text, i + 1);
				clearInterval(interval);
			}
		}, 100);
	};

	onMount(() => {
		type(title, 1);
	});
	let y = 0;
</script>

<svelte:window bind:scrollY={y} />

<div
	class="absolute -z-10 bg-[url('/images/house.jpeg')] bg-no-repeat bg-cover bg-fixed h-screen w-screen"
/>
<div class="relative -z-10 h-screen w-screen text-white drop-shadow-[0px_10px_5px_rgba(0,0,0,1)]">
	<div class="h-full flex flex-col items-center justify-center" style="padding-top: {y}px">
		<p class="text-5xl font-nunito font-bold">WELCOME TO</p>
		<p class="text-[120px] font-book font-bold -mt-4">{display}</p>
		<p class="text-5xl font-nunito font-bold">MIT Xi Chapter</p>
	</div>
</div>

<div class="px-40 pt-20 relative h-[800px] bg-stone-300 z-10 text-black">
	<div class="flex space-x-10">
		<div>
			<p class="text-5xl font-book font-black">Lifelong Brotherhood</p>
			<p class="pt-5 font-nunito text-3xl">
				ZBT has existed at MIT for over 100 years, and spent the last 50 of those nestled away at
				our home in Brookline. We are a brotherhood of over 50 members from across the United States
				and various foreign countries, representing a diverse array of majors at MIT and a broad
				range of on campus activities.
			</p>
		</div>
		<img class="w-1/2 rounded-xl" src="./images/zbt-stairs.jpeg" alt="zbt-stairs" />
	</div>
</div>
