<script lang="ts">
	import { Briefcase, GraduationCap, Code, Server } from '@lucide/svelte';
</script>

<section id="about" class="py-20">
	<div class="container mx-auto px-6">
		<h2 class="mb-12 text-center text-3xl font-bold text-white">About Me</h2>

		<div class="flex flex-col items-center gap-12 md:flex-row">
			<div class="md:w-1/3">
				<div class="overflow-hidden rounded-lg">
					<img src="/images/kyle.png" alt="Kyle Mendell" class="h-full w-full object-cover" />
				</div>
			</div>

			<div class="space-y-6 md:w-2/3">
				<p class="text-gray-300">
					I'm a support engineer, and open-source developer with a passion for building unique and
					functional software.<br /><br />

					Im currently working on <span class="text-cyan-400">Svelocker UI</span> as the Lead
					Maintainer, and <span class="text-cyan-400">Pocket ID</span> as a Secondary Maintainer.
				</p>

				<p class="text-gray-300">
					My <span class="text-cyan-400">favorite tech</span> includes
					<span class="text-cyan-400">GoLang</span>, Svelte, TypeScript, and Node.js.
				</p>

				<div class="flex flex-wrap gap-4 pt-4">
					<div class="flex items-center">
						<Code class="mr-2 h-5 w-5 text-cyan-400" />
						<span class="text-gray-300">Frontend Development</span>
					</div>
					<div class="flex items-center">
						<Server class="mr-2 h-5 w-5 text-cyan-400" />
						<span class="text-gray-300">Backend Development</span>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
