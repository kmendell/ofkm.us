<script lang="ts">
	import { Github, ExternalLink } from '@lucide/svelte';

	interface Project {
		title: string;
		description: string;
		image?: string;
		tags: string[];
		link?: string;
		github?: string;
	}

	const projects: Project[] = [
		{
			title: 'Svelocker UI',
			description: 'Simple and Modern Docker Registry UI. ',
			tags: ['SvelteKit', 'TypeScript', 'Tailwind CSS'],
			github: 'https://github.com/ofkm/svelocker-ui',
			image: '/images/svelocker.png'
		},
		{
			title: 'Pocket ID',
			description:
				'Pocket ID is a simple but powerful OIDC provider that allows users to authenticate with their passkeys to your services.',
			tags: ['SvelteKit', 'TypeScript', 'Tailwind CSS'],
			link: 'https://demo.pocket-id.org',
			github: 'https://github.com/pocket-id/pocket-id',
			image: '/images/pocket-id.png'
		},
		{
			title: 'Pocket ID Portal',
			description:
				'Example End User Portal for Accessing/Viewing information from Pocket ID using the API.',
			tags: ['SvelteKit', 'TypeScript', 'Tailwind CSS'],
			github: 'https://github.com/pocket-id/pocket-id-portal',
			image: '/images/pocket-id.png'
		}
	];
</script>

<section id="projects" class="py-20">
	<div class="container mx-auto px-6">
		<h2 class="mb-12 text-center text-3xl font-bold text-white">Projects</h2>

		<div class="space-y-12">
			{#each projects as project}
				<div class="border-b border-gray-800 pb-12">
					<div class="grid gap-8 md:grid-cols-2">
						<div>
							<h3 class="mb-4 text-2xl font-bold text-white">{project.title}</h3>
							<p class="mb-6 text-gray-300">{project.description}</p>

							<div class="mb-6 flex flex-wrap gap-2">
								{#each project.tags as tag}
									<span class="rounded-full border border-gray-700 px-3 py-1 text-xs text-gray-300">
										{tag}
									</span>
								{/each}
							</div>

							<div class="flex space-x-6">
								{#if project.github}
									<a
										href={project.github}
										target="_blank"
										rel="noopener noreferrer"
										class="flex items-center text-gray-400 transition-colors hover:text-cyan-400"
									>
										<Github class="mr-1 h-5 w-5" />
										<span>Source</span>
									</a>
								{/if}

								{#if project.link}
									<a
										href={project.link}
										target="_blank"
										rel="noopener noreferrer"
										class="flex items-center text-gray-400 transition-colors hover:text-cyan-400"
									>
										<ExternalLink class="mr-1 h-5 w-5" />
										<span>Live Demo</span>
									</a>
								{/if}
							</div>
						</div>

						<!-- Project image with fixed square size -->
						<div class="flex items-center justify-center">
							{#if project.image}
								<div class="h-40 w-40 overflow-hidden">
									<img src={project.image} alt={project.title} class="h-full w-full object-cover" />
								</div>
							{:else}
								<div class="flex h-64 w-64 items-center justify-center rounded-md bg-gray-800">
									<div class="text-center text-gray-600">
										<span class="text-6xl font-bold">{project.title.charAt(0)}</span>
									</div>
								</div>
							{/if}
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
