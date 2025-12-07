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
			tags: ['SvelteKit', 'TypeScript', 'Tailwind CSS', 'GoLang'],
			github: 'https://github.com/ofkm/svelocker-ui',
			image: '/images/svelocker.png'
		},
		{
			title: 'Arcane',
			description: 'Modern Docker Management, Designed for Everyone.',
			tags: ['SvelteKit', 'TypeScript', 'Tailwind CSS'],
			github: 'https://github.com/getarcaneapp/arcane',
			image: 'https://raw.githubusercontent.com/getarcaneapp/website/refs/heads/main/static/img/logo.svg'
		},
		{
			title: 'Pocket ID',
			description:
				'Pocket ID is a simple but powerful OIDC provider that allows users to authenticate with their passkeys to your services.',
			tags: ['SvelteKit', 'TypeScript', 'Tailwind CSS'],
			link: 'https://demo.pocket-id.org',
			github: 'https://github.com/pocket-id/pocket-id',
			image: '/images/pocket-id.png'
		}
	];
</script>

<section id="projects" class="py-20">
	<div class="container mx-auto px-6">
		<h2 class="mb-12 text-center text-3xl font-bold text-white">Projects</h2>

		<div class="grid gap-8 md:grid-cols-2">
			{#each projects as project}
				<div
					class="group relative overflow-hidden rounded-xl border border-gray-800 bg-gray-900/50 transition-all duration-300 hover:-translate-y-2 hover:border-cyan-500/50 hover:shadow-xl hover:shadow-cyan-500/10"
				>
					{#if project.image}
						<div class="aspect-video w-full overflow-hidden rounded-t-xl bg-gray-900">
							<img
								src={project.image}
								alt={project.title}
								class="h-full w-full object-contain transition-transform duration-500 group-hover:scale-110"
							/>
						</div>
					{:else}
						<div class="flex aspect-video w-full items-center justify-center bg-linear-to-br from-gray-800 to-gray-900 rounded-t-xl">
							<span class="text-4xl font-bold text-gray-400">{project.title.charAt(0)}</span>
						</div>
					{/if}

					<div class="p-6">
						<h3 class="mb-2 text-2xl font-bold text-white group-hover:text-cyan-400 transition-colors">
							{project.title}
						</h3>
						<p class="mb-4 text-gray-400 line-clamp-3">{project.description}</p>

						<div class="mb-6 flex flex-wrap gap-2">
							{#each project.tags as tag}
								<span
									class="rounded-full border border-gray-700 bg-gray-800/50 px-3 py-1 text-xs text-gray-300"
								>
									{tag}
								</span>
							{/each}
						</div>

						<div class="flex space-x-4">
							{#if project.github}
								<a
									href={project.github}
									target="_blank"
									rel="noopener noreferrer"
									class="flex items-center text-sm text-gray-400 transition-colors hover:text-cyan-400"
								>
									<Github class="mr-1 h-4 w-4" />
									<span>Source</span>
								</a>
							{/if}

							{#if project.link}
								<a
									href={project.link}
									target="_blank"
									rel="noopener noreferrer"
									class="flex items-center text-sm text-gray-400 transition-colors hover:text-cyan-400"
								>
									<ExternalLink class="mr-1 h-4 w-4" />
									<span>Live Demo</span>
								</a>
							{/if}
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
