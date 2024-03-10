<script lang="ts">
	export let big: boolean = false;
</script>

<div class="flex min-w-48 max-w-48">
	<div class="min-w-36 max-w-36 grow-0 self-center py-6 text-right">
		<slot name="info" />
	</div>
	<div class="relative">
		<div class="absolute h-full w-10 border-r-2 border-dotted border-r-[#7A9299]/50">
			{#if big}
				<div
					class="absolute -right-0.5 -top-0.5 h-3 w-[2px] -translate-x-1 rotate-45 bg-[#7A9299]"
				></div>
				<div
					class="absolute -right-0.5 -top-0.5 h-3 w-[2px] translate-x-1 -rotate-45 bg-[#7A9299]"
				></div>
				<div
					class="absolute right-0 top-1/2 h-7 w-7 -translate-y-1/2 translate-x-[55%] rounded-full bg-blue-700"
				>
					<div
						class="absolute right-1/2 top-1/2 h-2 w-2 -translate-y-1/2 translate-x-1/2 rounded-full bg-white"
					></div>
				</div>
			{/if}

			{#if !big}
				<div
					class="absolute right-0 top-1/2 h-4 w-4 -translate-y-1/2 translate-x-[55%] rounded-full bg-blue-700"
				>
					<div
						class="absolute right-1/2 top-1/2 h-3 w-3 -translate-y-1/2 translate-x-1/2 rounded-full bg-white"
					></div>
				</div>
			{/if}
		</div>
	</div>
</div>
