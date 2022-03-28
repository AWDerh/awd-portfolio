<script lang="ts">
	import { onMount } from 'svelte';
	import FaMousePointer from 'svelte-icons/fa/FaMousePointer.svelte';

	export let x: Number | String = 0;
	export let y: Number | String = 0;

	export const pointer = {
		movePointer: (new_x, new_y) => {
			x = new_x;
			y = new_y;
		}
	};
</script>

<div class="cursor h-5 w-5 absolute" style="top: {y}; left: {x};">
	<FaMousePointer />
</div>

<style>
	.cursor {
		transition-property: top left;
		transition-duration: 1s;
	}
</style>
