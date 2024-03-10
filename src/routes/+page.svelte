<script lang="ts">
	import FaceMain from '../lib/face_main.png';
	import SocialIconDuggup from '$lib/social_icon_duggup.svelte';
	import Button from './Button.svelte';
	import LinkExternal from '$lib/link-external.svelte';
	import Threedots from '$lib/threedots.svelte';
	import Card from './Card.svelte';
	import Sam from '$lib/sam_altman.png';
	import Jobs from '$lib/steve_jobs.png';
	import Timeline from './VerticalLine.svelte';
	import SocialDuggup from '$lib/social_icon_duggup.svelte';
	import DesktopSetup from '$lib/desktop_setup.png';
	import OmissionImage from '$lib/omission_image.png';
	import SocialBetterUp from '$lib/social_icon_betterup.svg';

	let followed = $state(false);
</script>

<div class="flex flex-col justify-start">
	<div class="flex justify-between gap-10 px-28 pb-4 pt-12">
		<div class="flex w-32 flex-col items-center justify-between gap-2 text-center font-[700]">
			<img src={FaceMain} alt="" width="120" height="120" />
			<span class="text-2xl">Krishna Kiran</span>
		</div>
		<div class="flex flex-grow flex-col gap-8">
			<div class="flex w-full items-start justify-between">
				<desc class="max-w-[592px] p-1 text-sm"
					>Co-Founder and CEO at Duggup - Social network for people in tech. Ex-Amazon Head of
					Engineering. I write hot-takes on building a business, shipping delightful products and
					accelerating product and career growth.</desc
				>
				<div class="flex flex-col items-end">
					<SocialIconDuggup width={'36'} height={'36'} />
					<span class="text-base font-bold">Duggup</span>
					<span class="text-xs">Co-founder and CEO</span>
				</div>
			</div>
			<div class="flex items-center justify-between">
				<div
					on:click={() => (followed = !followed)}
					role="button"
					tabindex="0"
					on:keydown={(e) => {
						console.log(e);
					}}
				>
					{#if followed}
						<Button>
							<span slot="text">Unfollow</span>
						</Button>
					{:else}
						<Button>
							<span slot="text">Follow</span>
						</Button>
					{/if}
				</div>
				<div class="flex items-center gap-5">
					<a href="/" class="flex items-center gap-2">
						<span>My Website</span>
						<LinkExternal />
					</a>
					<Threedots />
				</div>
			</div>
		</div>
	</div>

	<div class="flex flex-col">
		<div class="flex">
			<Timeline big={false}>
				<div class="text-right text-xs text-[#7A9299]" slot="info">Dec 2023</div>
			</Timeline>
			<div class="flex justify-start gap-10 px-10 py-5">
				<Card image={Jobs}>
					<div slot="info">No amount of technology can convert a bad story into a good story.</div>
				</Card>
				<Card image={Sam}>
					<div slot="info">
						Most people don't have original ideas. Here is how Sam Altman pushes himself to have
						unpopular ideas.
					</div>
				</Card>
			</div>
		</div>
		<div class="flex">
			<Timeline big={true}>
				<div class="flex flex-col items-end" slot="info">
					<SocialDuggup width={'48'} height={'48'} />
					<div class="font-bold">Duggup</div>
					<div class="text-xs text-[#7A9299]">San Francisco Bay Area</div>
					<div class="text-xs text-[#7A9299]">Joined</div>
					<div class="text-xs text-[#7A9299]">Nov 2023</div>
				</div>
			</Timeline>
			<div class="flex flex-col items-start justify-center px-14 py-5">
				<div class="text-xl font-bold">Co-Founder and CEO</div>
				<div class="text-xs text-[#7A9299]">Full-time · Remote</div>
			</div>
		</div>
		<div class="flex">
			<Timeline big={false}>
				<div class="text-right text-xs text-[#7A9299]" slot="info">Dec 2023</div>
			</Timeline>
			<div class="flex justify-start gap-10 px-10 py-5">
				<Card image={DesktopSetup}>
					<div slot="info">
						Startup Lesson I am reflecting. Don't build for the "average person".
					</div>
				</Card>
				<Card image={OmissionImage}>
					<div slot="info">Your biggest regrets at 80 will be acts of omission.</div>
				</Card>
			</div>
		</div>
		<div class="flex">
			<Timeline big={true}>
				<div class="flex flex-col items-end" slot="info">
					<img src={SocialBetterUp} alt="BetterUp logo" />
					<div class="font-bold">BetterUp</div>
					<div class="text-xs text-[#7A9299]">San Francisco Bay Area</div>
					<div class="text-xs text-[#7A9299]">Joined</div>
					<div class="text-xs text-[#7A9299]">Sep 2022</div>
				</div>
			</Timeline>
			<div class="flex flex-col items-start justify-center px-14 py-5">
				<div class="text-xl font-bold">VP Engineering</div>
				<div class="text-xs text-[#7A9299]">Full-time</div>
			</div>
		</div>
	</div>
</div>
