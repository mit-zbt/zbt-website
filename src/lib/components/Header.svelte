<script>
	const links = [
		{ name: 'Rush', url: '/rush' },
		{ name: 'Events', url: '/events' },
		{ name: 'Brothers', url: '/brothers' },
		{ name: 'House', url: '/house' },
		{ name: 'History', url: '/history' },
		{ name: 'Alumni', url: '/alumni' }
	];
	let y = 0;
</script>

<svelte:window bind:scrollY={y} />

<header
	class="px-40 fixed w-screen z-20"
	style="background-color: rgba(75,158,252,{Math.min(y / 200, 1)});"
>
	<div class="flex justify-between text-white py-3">
		<a href="/" class="text-4xl font-extrabold text-center flex font-book">
			<img class="h-10 mr-3" src="./images/zbt-crest.png" alt="zbt-crest" />
			<p>ZBT</p>
		</a>
		<div class="flex justify-around space-x-1">
			{#each links as link}
				<a
					href={link.url}
					class="font-nunito text-2xl font-bold flex items-center px-3 transition-colors rounded-xl hover:bg-cyan-600"
					>{link.name}</a
				>
			{/each}
		</div>
	</div>
</header>
