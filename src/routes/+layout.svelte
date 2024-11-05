<script lang="ts">
	import * as Sidebar from '$lib/components/ui/sidebar/index.js';
	import AppSidebar from '$lib/components/SideBar.svelte';

	import '../app.css';
	let { children } = $props();
</script>

<Sidebar.Provider>
	<AppSidebar />
	<main class="p-3">
		<Sidebar.Trigger />
		{@render children?.()}
	</main>
</Sidebar.Provider>
