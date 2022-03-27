<script lang="ts">
	import { onMount } from 'svelte';

	class Tab {
		public url: string;
		public title: string;
		public content: any;

		public async loadTab() {
			this.content = await fetch(this.url);
			return this.content;
		}
	}

	let tab1 = new Tab();
	tab1.url = 'https://youtube.com';
	tab1.title = 'Youtube';

	let tabs: Array<Tab> = [tab1];

	function loadTabs() {
		tabs.forEach((x) => x.loadTab());
	}

	onMount(() => {
		loadTabs();
	});
</script>

<section class="h-full w-full">
	<header class="flex w-full bg-black">
		<div class="tabs flex-grow">
			{#each tabs as tab}
				<div class="tab">{tab.title}</div>
			{/each}
		</div>
		<div class="controls">
			<button>_</button>
			<button>[]</button>
			<button>X</button>
		</div>
	</header>
	<iframe />
</section>
