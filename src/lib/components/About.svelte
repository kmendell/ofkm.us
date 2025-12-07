<script lang="ts">
	import { Briefcase, GraduationCap, Code, Server } from '@lucide/svelte';
	import { Motion } from 'svelte-motion';
</script>

<section id="about" class="py-20 relative">
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
			<div use:motion>
				<h2 class="mb-12 text-center text-3xl font-bold text-white">About Me</h2>

				<div class="flex flex-col items-center gap-12 md:flex-row">
					<div class="md:w-1/3">
						<div class="overflow-hidden rounded-2xl border border-white/10 shadow-2xl">
							<img src="/images/kyle.png" alt="Kyle Mendell" class="h-full w-full object-cover transition-transform duration-500 hover:scale-105" />
						</div>
					</div>

					<div class="space-y-6 md:w-2/3">
						<p class="text-gray-300 text-lg leading-relaxed">
							I'm a support engineer, and open-source developer with a passion for building unique and
							functional software.<br /><br />

							I'm currently working on <span class="text-primary-400 font-semibold">Arcane</span> as the Lead
							Maintainer, and <span class="text-primary-400 font-semibold">Pocket ID</span> as a Secondary Maintainer.
						</p>

						<p class="text-gray-300 text-lg leading-relaxed">
							My <span class="text-primary-400 font-semibold">favorite tech</span> includes
							<span class="text-primary-400 font-semibold">GoLang</span>, Svelte, TypeScript, and Node.js.
						</p>

						<div class="flex flex-wrap gap-4 pt-4">
							<div class="flex items-center rounded-full bg-primary-500/10 px-4 py-2 border border-primary-500/20">
								<Code class="mr-2 h-5 w-5 text-primary-400" />
								<span class="text-gray-200">Frontend Development</span>
							</div>
							<div class="flex items-center rounded-full bg-primary-500/10 px-4 py-2 border border-primary-500/20">
								<Server class="mr-2 h-5 w-5 text-primary-400" />
								<span class="text-gray-200">Backend Development</span>
							</div>
						</div>
					</div>
				</div>
			</div>
		</Motion>
	</div>
</section>
