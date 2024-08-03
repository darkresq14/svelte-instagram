<script lang="ts">
	import Sidebar from '@/components/Sidebar.svelte';

	let { children } = $props();
</script>

<Sidebar />
<div class="ml-[73px] py-8 md:ml-[244px]">
	{@render children()}
</div>
