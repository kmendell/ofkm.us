<script lang="ts">
	import { Mail, Github, Linkedin, Twitter } from '@lucide/svelte';
</script>

<section id="contact" class="py-20">
	<div class="container mx-auto px-6">
		<h2 class="mb-8 text-center text-3xl font-bold text-white">Get in touch</h2>

		<div class="mx-auto max-w-md text-center">
			<p class="mb-8 text-gray-300">
				Feel free to reach out if you have a question, or just want to connect.
			</p>

			<a
				href="mailto:kmendell@ofkm.us"
				class="mb-8 flex items-center justify-center gap-2 text-lg text-cyan-400 hover:underline"
			>
				<Mail class="h-5 w-5" />
				kmendell@ofkm.us
			</a>

			<div class="flex justify-center space-x-8">
				<a
					href="https://github.com/kmendell"
					target="_blank"
					rel="noopener noreferrer"
					class="text-gray-400 transition-colors hover:text-cyan-400"
					aria-label="GitHub"
				>
					<Github class="h-6 w-6" />
				</a>
				<a
					href="https://linkedin.com/in/kyle-mendell"
					target="_blank"
					rel="noopener noreferrer"
					class="text-gray-400 transition-colors hover:text-cyan-400"
					aria-label="LinkedIn"
				>
					<Linkedin class="h-6 w-6" />
				</a>
				<a
					href="https://twitter.com/OfficialKSM_"
					target="_blank"
					rel="noopener noreferrer"
					class="text-gray-400 transition-colors hover:text-cyan-400"
					aria-label="Twitter"
				>
					<Twitter class="h-6 w-6" />
				</a>
			</div>
		</div>
	</div>
</section>
