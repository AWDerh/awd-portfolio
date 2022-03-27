<script>
	import IconPowerShell from '$lib/icon-powershell.png';
	import FaRegWindowMinimize from 'svelte-icons/fa/FaRegWindowMinimize.svelte';
</script>

<section class="terminal-container h-full w-full">
	<header class="h-7 bg-black flex flex-row">
		<img src={IconPowerShell} alt="PowerShell" class="h-full p-1" />
		<span class="flex-grow text-left">Windows Powershell</span>
	</header>
	<article>
		<div>
			<p>Custom Shell</p>
			<p>Copyright (C) Microsoft Corporation. All rights reserved.</p>
		</div>
		<br />
		<div>
			<p>PS C:\Users\Abdul Derh></p>
		</div>
	</article>
</section>

<style>
	section {
		background-color: rgb(1, 36, 86, 0.5);
		border: solid 1px #333;
		color: white;
		font-family: 'Consolas', 'sans-serif';
	}
</style>
