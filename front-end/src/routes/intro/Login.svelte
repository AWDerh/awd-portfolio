<script lang="ts">
	import TypeWriter from 'svelte-typewriter';
	import { fade } from 'svelte/transition';
</script>

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
