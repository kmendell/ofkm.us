<script lang="ts">
	import { Mail, Github, Linkedin, Twitter } from '@lucide/svelte';
	import { Motion } from 'svelte-motion';
</script>

<section id="contact" class="py-20 relative">
	<div class="container mx-auto px-6 relative z-10">
		<Motion
			{...{
				initial: { opacity: 0, y: 20 },
				whileInView: { opacity: 1, y: 0 },
				viewport: { once: true },
				transition: { duration: 0.5 }
			}}
			let:motion
		>
			<div use:motion class="mx-auto max-w-2xl rounded-2xl border border-white/10 bg-black/40 p-8 backdrop-blur-md md:p-12">
				<h2 class="mb-6 text-center text-3xl font-bold text-white">Get in touch</h2>

				<div class="mx-auto max-w-md text-center">
					<p class="mb-8 text-gray-300">
						Feel free to reach out if you have a question, or just want to connect.
					</p>

					<a
						href="mailto:ksm@ofkm.us"
						class="group mb-10 flex items-center justify-center gap-3 rounded-full bg-white/5 px-6 py-3 text-lg font-medium text-white transition-all hover:bg-primary-500 hover:shadow-[0_0_20px_rgba(14,165,233,0.5)]"
					>
						<Mail class="h-5 w-5 text-primary-400 group-hover:text-white transition-colors" />
						<span>ksm@ofkm.us</span>
					</a>

					<div class="flex justify-center gap-6">
						<a
							href="https://github.com/kmendell"
							target="_blank"
							rel="noopener noreferrer"
							class="group flex h-12 w-12 items-center justify-center rounded-full bg-white/5 text-gray-400 transition-all hover:bg-white/10 hover:text-white hover:-translate-y-1"
							aria-label="GitHub"
						>
							<Github class="h-6 w-6" />
						</a>
						<a
							href="https://linkedin.com/in/kyle-mendell"
							target="_blank"
							rel="noopener noreferrer"
							class="group flex h-12 w-12 items-center justify-center rounded-full bg-white/5 text-gray-400 transition-all hover:bg-[#0077b5] hover:text-white hover:-translate-y-1"
							aria-label="LinkedIn"
						>
							<Linkedin class="h-6 w-6" />
						</a>
						<a
							href="https://twitter.com/OfficialKSM_"
							target="_blank"
							rel="noopener noreferrer"
							class="group flex h-12 w-12 items-center justify-center rounded-full bg-white/5 text-gray-400 transition-all hover:bg-[#1DA1F2] hover:text-white hover:-translate-y-1"
							aria-label="Twitter"
						>
							<Twitter class="h-6 w-6" />
						</a>
					</div>
				</div>
			</div>
		</Motion>
	</div>
</section>
