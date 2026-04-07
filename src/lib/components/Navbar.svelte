<script lang="ts">
	import { base } from '$app/paths';
	import { page } from '$app/stores';

	let mobileOpen = $state(false);

	const navItems = [
		{ href: '/weapons', label: 'Weapons' },
		{ href: '/armor', label: 'Armor' }
	];
</script>

<nav class="bg-gray-900 border-b border-gray-700">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="flex h-16 items-center justify-between">
			<div class="flex items-center gap-8">
				<a href={base + '/'} class="text-xl font-bold text-amber-400 tracking-wide">FFI</a>

				<div class="hidden sm:flex gap-1">
					{#each navItems as item}
						<a
							href={base + item.href}
							class="rounded-md px-4 py-2 text-sm font-medium transition-colors
								{$page.url.pathname.startsWith(base + item.href)
								? 'bg-gray-700 text-white'
								: 'text-gray-300 hover:bg-gray-800 hover:text-white'}"
						>
							{item.label}
						</a>
					{/each}
				</div>
			</div>

			<button
				class="sm:hidden inline-flex items-center justify-center rounded-md p-2 text-gray-400 hover:bg-gray-800 hover:text-white transition-colors"
				onclick={() => (mobileOpen = !mobileOpen)}
				aria-label="Toggle menu"
			>
				{#if mobileOpen}
					<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
						<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
					</svg>
				{:else}
					<svg class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
						<path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
					</svg>
				{/if}
			</button>
		</div>
	</div>

	{#if mobileOpen}
		<div class="sm:hidden border-t border-gray-700 px-4 pb-3 pt-2 space-y-1">
			{#each navItems as item}
				<a
					href={base + item.href}
					onclick={() => (mobileOpen = false)}
					class="block rounded-md px-3 py-2 text-base font-medium transition-colors
						{$page.url.pathname.startsWith(base + item.href)
						? 'bg-gray-700 text-white'
						: 'text-gray-300 hover:bg-gray-800 hover:text-white'}"
				>
					{item.label}
				</a>
			{/each}
		</div>
	{/if}
</nav>
