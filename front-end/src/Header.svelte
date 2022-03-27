<script>
	import DarkMode from './DarkMode.svelte';

	// Social icons
	import FaLinkedinIn from 'svelte-icons/fa/FaLinkedinIn.svelte';
	import FaGithub from 'svelte-icons/fa/FaGithub.svelte';
	import FaMedium from 'svelte-icons/fa/FaMedium.svelte';
</script>

<nav class="flex flex-row items-center gap-10 p-3 h-12">
	<div class="flex-grow text-center pl-4 h-full">
		<!-- <a href="/home">Home</a>
		<a href="/portfolio">Portfolio</a> -->
	</div>
	<div class="flex flex-row gap-5 h-full">
		<a href="https://github.com/AWDerh"><FaGithub /></a>
		<a href="https://medium.com/@abdul.derh"><FaMedium /></a>
		<a href="https://www.linkedin.com/in/awderh/"><FaLinkedinIn /></a>
	</div>
	<div class="h-full">
		<DarkMode />
	</div>
</nav>

<style>
</style>
