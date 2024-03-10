<script lang="ts">
	import Navlogo from '$lib/nav_logo.svelte';
	import HomeIcon from '$lib/Home.svelte';
	import ExploreIcon from '$lib/Explore.svelte';
	import LearnIcon from '$lib/Learn.svelte';
	import FaceLogin from '$lib/face_login.png';
	import ChevronDownIcon from '$lib/chevron-down.svelte';
	import Button from './Button.svelte';
	import PlusSquare from '$lib/plus_square.svelte';
	let color = 'black';

	function handleMouseOver() {
		console.log('hello');
		color = 'white';
	}

	function handleMouseOut() {
		color = 'black';
	}
</script>

<nav
	class="mx-auto flex h-20 max-w-[1424px] items-center justify-between border-b border-dotted border-black"
>
	<div><Navlogo /></div>
	<div class="flex items-center justify-between gap-16">
		<div class="flex items-center justify-between gap-12">
			<div class="flex items-center justify-between gap-8 text-sm">
				<a href="/" class="flex items-center justify-between gap-3">
					<HomeIcon />
					<span>Home</span>
				</a>
				<a href="/" class="flex items-center justify-between gap-3">
					<ExploreIcon />
					<span>Explore</span>
				</a>
				<a href="/" class="flex items-center justify-between gap-3">
					<LearnIcon />
					<span>Learn</span>
				</a>
			</div>
			<div
				on:mouseover={handleMouseOver}
				on:mouseleave={handleMouseOut}
				on:focus={handleMouseOver}
				on:blur={handleMouseOut}
				role="cell"
				tabindex="0"
			>
				<Button>
					<span slot="icon">
						<!-- <PlusSquare /> -->
						<svelte:component this={PlusSquare} data={color} />
					</span>
					<span slot="text">Post</span>
				</Button>
			</div>
		</div>
		<div class="flex items-center justify-center gap-4">
			<img src={FaceLogin} alt="" width="46" height="46" />
			<span class="text-xl">Krishna Kiran</span>
			<ChevronDownIcon />
		</div>
	</div>
</nav>
