<script lang="ts">
	import Explore from '@/icons/Explore.svelte';
	import Home from '@/icons/Home.svelte';
	import Logo from '@/icons/Logo.svelte';
	import Messenger from '@/icons/Messenger.svelte';
	import NewPost from '@/icons/NewPost.svelte';
	import Notifications from '@/icons/Notifications.svelte';
	import Reels from '@/icons/Reels.svelte';
	import Search from '@/icons/Search.svelte';
	import { cn } from '@/utils';
	import { CircleUser, Instagram } from 'lucide-svelte';

	const sidebarItems = [
		{ text: 'home', icon: Home, href: '/' },
		{ text: 'search', icon: Search },
		{ text: 'explore', icon: Explore },
		{ text: 'reels', icon: Reels },
		{ text: 'messages', icon: Messenger },
		{ text: 'notifications', icon: Notifications },
		{ text: 'create', icon: NewPost },
		{ text: 'profile', icon: CircleUser, href: '/' }
	];
</script>

<aside
	class="fixed flex h-full min-h-screen w-fit flex-col border-r bg-background p-3 md:w-[244px]"
>
	<div class="my-8 pl-3">
		<div class="hidden w-fit md:inline-block">
			<Logo />
		</div>
		<Instagram class="md:hidden" />
	</div>

	<div class="flex flex-1 flex-col gap-2">
		{#each sidebarItems as { text, icon, href }}
			<svelte:element
				this={href ? 'a' : text === 'create' ? 'button' : 'div'}
				{href}
				role="none"
				class="flex cursor-pointer items-center gap-1 rounded-md p-3 text-sm capitalize hover:bg-muted"
			>
				<svelte:component this={icon} />
				<div class={cn('ml-4 hidden md:inline-block', { 'font-bold': text === 'home' })}>
					{text}
				</div>
			</svelte:element>
		{/each}
	</div>
</aside>
