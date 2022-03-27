<script>
	import FaWindows from 'svelte-icons/fa/FaWindows.svelte';
	import FaSpinner from 'svelte-icons/fa/FaSpinner.svelte';
</script>

<div class="grid grid-rows-2 grid-cols-1 h-full ">
	<div id="os-logo" class="h-32 my-auto">
		<FaWindows />
	</div>
	<div id="os-loading" class="h-8 my-auto animate-spin">
		<FaSpinner />
	</div>
</div>

<style>
</style>
