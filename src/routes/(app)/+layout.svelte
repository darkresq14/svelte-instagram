<script lang="ts">
	import Sidebar from '@/components/Sidebar.svelte';
	import { ModeWatcher } from 'mode-watcher';

	let { children } = $props();
</script>

<ModeWatcher />
<Sidebar />
{@render children()}
