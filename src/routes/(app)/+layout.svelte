<script lang="ts">
	import Sidebar from '@/components/Sidebar.svelte';

	let { children } = $props();
</script>

<Sidebar />
{@render children()}
