<script lang="ts">
	export let image: string;
</script>

<div class="w-[21rem] overflow-hidden rounded-xl border">
	<img src={image} alt="" class="h-32 w-full rounded-t-xl object-cover" />

	<div class="overflow-hidden px-5 py-5">
		<div class="line-clamp-2 text-sm">
			<slot name="info">Hello</slot>
		</div>
	</div>
</div>
