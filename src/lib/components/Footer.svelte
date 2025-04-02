<script lang="ts">
	import { Github, Linkedin, Twitter } from '@lucide/svelte';

	const currentYear = new Date().getFullYear();
</script>

<footer class="border-t border-gray-800 py-6 text-center text-gray-500">
	<div class="container mx-auto px-6">
		<p>{currentYear} Kyle Mendell.</p>
	</div>
</footer>
