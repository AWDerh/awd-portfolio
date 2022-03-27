<script>
	import 'node-localstorage/register';

	import FaSun from 'svelte-icons/fa/FaSun.svelte';
	import FaRegMoon from 'svelte-icons/fa/FaRegMoon.svelte';

	function isDarkMode() {
		return document.documentElement.classList.contains('dark');
	}

	function useDarkMode() {
		if ('theme' in localStorage) return localStorage.theme === 'dark';
		return true;
	}

	function setDarkMode() {
		document.documentElement.classList.add('dark');
	}

	function setLightMode() {
		document.documentElement.classList.remove('dark');
	}

	function autoDarkMode() {
		localStorage.removeItem('theme');
	}

	function saveThemePreferences() {
		if (isDarkMode()) {
			localStorage.theme = 'dark';
		} else {
			localStorage.theme = 'light';
		}
	}

	function toggleDarkMode() {
		if (isDarkMode()) {
			setLightMode();
		} else {
			setDarkMode();
		}
		saveThemePreferences();
	}

	let dark_mode = useDarkMode();
</script>

<button on:click={toggleDarkMode} class="h-6">
	<!--
        not a fan of this semi-custom syntax...  
        Sometimes it's like the industry has learned nothing over the past few
        years. For the love of god, stop making new syntax!!!
    -->
	{#if dark_mode}
		<FaRegMoon />
	{:else}
		<!-- 🤦‍♂️-->
		<FaSun />
	{/if}
	<!-- 🤦‍♂️-->
</button>
