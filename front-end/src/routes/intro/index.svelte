<script lang="ts">
	import Bootup from './Bootup.svelte';
	import Terminal from './Terminal.svelte';
	import WindowsDarkBackground from '$lib/win-dark-bg.webp';
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';

	import FaWindows from 'svelte-icons/fa/FaWindows.svelte';
	import IconWindowsExplorer from '$lib/icon-explorer.png';
	import IconChrome from '$lib/icon-chrome.png';
	import IconPowerShell from '$lib/icon-powershell.png';
	import IconVSCode from '$lib/icon-vscode.png';
	import IconSolidWorks from '$lib/icon-sldwrks.png';
	import FaVolumeDown from 'svelte-icons/fa/FaVolumeDown.svelte';
	import FaWifi from 'svelte-icons/fa/FaWifi.svelte';
	import TypeWriter from 'svelte-typewriter';

	import FaMousePointer from 'svelte-icons/fa/FaMousePointer.svelte';

	// import Chrome from './Chrome.svelte';

	let monitor_container: HTMLDivElement;
	let bootup_container: HTMLDivElement;
	let os_container: HTMLDivElement;
	let pointer_container: HTMLDivElement;
	let current_date: Date;
	let current_time_str: string;
	let current_date_str: string;

	function updateDateTime() {
		current_date = new Date();
		current_date_str = current_date.toLocaleDateString();
		current_time_str = current_date.toLocaleTimeString();
	}

	let scene = 0;
	function next() {
		scene = scene + 1;
		if (scene == 1) {
			setTimeout(next, 2000);
		} else if (scene == 2) {
		}
	}

	let show_terminal: boolean = false;

	updateDateTime();

	setInterval(updateDateTime, 333);

	onMount(() => {
		setTimeout(next, 1000);
	});
</script>

<div id="monitor-container" class="block w-screen h-screen bg-black overflow-clip">
	{#if scene == 0}
		<div
			id="bootup-container"
			class="transition m-auto w-full h-full p-3 text-blue-400"
			bind:this={bootup_container}
			in:fade
			out:fade
		>
			<Bootup />
		</div>
	{:else}
		<div class="cursor h-5 w-5 absolute top-1/2 left-1/2" bind:this={pointer_container}>
			<FaMousePointer />
		</div>
		<div
			id="os-container"
			bind:this={os_container}
			class="w-full h-full bg-cover bg-no-repeat bg-center {scene == 1 ? 'blur-sm' : ''}"
			style="background-image: url('{WindowsDarkBackground}')"
			in:fade
		>
			{#if scene == 2}
				<header class="toolbar flex flex-row gap-9 w-full h-12 bg-black">
					<div class="hover:text-blue-600 hover:bg-blend-lighten p-3"><FaWindows /></div>
					<div class="flex grow gap-0">
						<div class="icon p-3 hover:bg-gray-700">
							<img src={IconWindowsExplorer} class="h-full" alt="Windows Explorer" />
						</div>
						<div class="icon p-3 hover:bg-gray-700">
							<img src={IconChrome} class="h-full" alt="Chrome Browser" />
						</div>
						<div class="icon p-3 hover:bg-gray-700">
							<img src={IconPowerShell} class="h-full" alt="Powershell" />
						</div>
						<div class="icon p-3 hover:bg-gray-700">
							<img src={IconVSCode} class="h-full" alt="VSCode" />
						</div>
						<div class="icon p-3 hover:bg-gray-700">
							<img src={IconSolidWorks} class="h-full" alt="SolidWorks" />
						</div>
					</div>
					<div class="flex gap-0 items-center">
						<div class="icon p-3 h-full hover:bg-gray-700"><FaVolumeDown /></div>
						<div class="icon p-4 h-full hover:bg-gray-700"><FaWifi /></div>
						<div class="p-3 text-center hover:bg-gray-700">
							<div class="text-xs">{current_time_str}</div>
							<div class="text-xs">{current_date_str}</div>
						</div>
					</div>
				</header>
				{#if show_terminal}
					<div
						id="terminal"
						class="w-1/3 h-1/3 relative left-1/3 top-1/3 -translate-y-1/2"
						in:fade={{ delay: 1000 }}
					>
						<Terminal />
					</div>
				{/if}
			{/if}
		</div>
		{#if scene == 1}
			<div
				class="block w-72 absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 text-center"
				in:fade
				out:fade
			>
				<img
					alt=""
					class="rounded-full h-48 mx-auto"
					src="https://media-exp1.licdn.com/dms/image/C4E03AQEVw3Y5-jGqSw/profile-displayphoto-shrink_800_800/0/1632075240706?e=1652918400&v=beta&t=sCkD7V8GWNn6ik1gazqmJvZDehUWNfFHKi46g9eLEbM"
				/>
				<h1 class="text-5xl my-3">Abdul Derh</h1>
				<div
					class="mt-7 bg-white text-left h-7 w-full rounded-sm p-1 text-black overflow-hidden resize-none editable"
					type="password"
					placeholder="Password"
				>
					<TypeWriter delay="1000">**********</TypeWriter>
				</div>
				<p class="text-gray-300 mt-5">Reset Password</p>
				<p class="text-gray-300 mt-5">Sign-in Options</p>
			</div>
		{/if}
	{/if}
</div>

<style>
	#monitor-container {
		background-color: #060606;
		color: white;
	}
	#os-container {
		background-color: #060606;
	}
	#os-container > header {
	}
	#bootup-container {
	}
</style>
