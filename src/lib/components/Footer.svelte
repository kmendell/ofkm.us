<script lang="ts">
	import { Github, Linkedin, Twitter, Mail } from '@lucide/svelte';

	const currentYear = new Date().getFullYear();
</script>

<footer class="border-t border-white/10 bg-black py-12 text-center text-gray-500">
	<div class="container mx-auto px-6">
		<div class="mb-8 flex justify-center space-x-6">
			<a
				href="https://github.com/kmendell"
				target="_blank"
				rel="noopener noreferrer"
				class="text-gray-400 transition-colors hover:text-primary-400"
				aria-label="GitHub"
			>
				<Github class="h-5 w-5" />
			</a>
			<a
				href="https://linkedin.com/in/kyle-mendell"
				target="_blank"
				rel="noopener noreferrer"
				class="text-gray-400 transition-colors hover:text-primary-400"
				aria-label="LinkedIn"
			>
				<Linkedin class="h-5 w-5" />
			</a>
			<a
				href="https://twitter.com/OfficialKSM_"
				target="_blank"
				rel="noopener noreferrer"
				class="text-gray-400 transition-colors hover:text-primary-400"
				aria-label="Twitter"
			>
				<Twitter class="h-5 w-5" />
			</a>
			<a
				href="mailto:ksm@ofkm.us"
				class="text-gray-400 transition-colors hover:text-primary-400"
				aria-label="Email"
			>
				<Mail class="h-5 w-5" />
			</a>
		</div>
		<p class="text-sm text-gray-600">
			&copy; {currentYear} Kyle Mendell. All rights reserved.
		</p>
	</div>
</footer>
