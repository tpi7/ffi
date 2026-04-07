<script lang="ts">
	import { i18n } from "$lib/i18n";
	import { ParaglideJS } from "@inlang/paraglide-sveltekit";
	import Navbar from "$lib/components/Navbar.svelte";
	import '../app.css';
	let { children } = $props();
</script>

<ParaglideJS {i18n}>
	<Navbar />
	<main class="min-h-screen bg-gray-950 text-gray-100">
		{@render children()}
	</main>
</ParaglideJS>
