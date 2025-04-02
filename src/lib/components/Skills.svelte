<script lang="ts">
	import { Monitor, Server, Wrench } from '@lucide/svelte';

	interface SkillCategory {
		name: string;
		icon: any;
		skills: Array<{
			name: string;
			icon: string;
		}>;
	}

	const skillCategories: SkillCategory[] = [
		{
			name: 'Frontend',
			icon: Monitor,
			skills: [
				{ name: 'Svelte/SvelteKit', icon: 'devicon-svelte-plain' },
				{ name: 'TypeScript', icon: 'devicon-typescript-plain' },
				{ name: 'HTML/CSS', icon: 'devicon-html5-plain' },
				{ name: 'Tailwind CSS', icon: 'devicon-tailwindcss-plain' }
			]
		},
		{
			name: 'Backend',
			icon: Server,
			skills: [
				{ name: 'Node.js', icon: 'devicon-nodejs-plain' },
				{ name: 'GoLang', icon: 'devicon-go-plain' },
				{ name: 'PostgreSQL', icon: 'devicon-postgresql-plain' },
				{ name: 'SQLite', icon: 'devicon-sqlite-plain' }
			]
		},
		{
			name: 'Tools & Others',
			icon: Wrench,
			skills: [
				{ name: 'Git', icon: 'devicon-git-plain' },
				{ name: 'Docker', icon: 'devicon-docker-plain' },
				{ name: 'VS Code', icon: 'devicon-vscode-plain' }
			]
		}
	];
</script>

<section id="skills" class="py-20">
	<div class="container mx-auto px-6">
		<h2 class="mb-3 text-center text-3xl font-bold text-white">Skills & Expertise</h2>
		<p class="mx-auto mb-12 max-w-2xl text-center text-gray-400">
			Here's an overview of my technical skills and areas of expertise.
		</p>

		<div class="grid gap-10 md:grid-cols-3">
			{#each skillCategories as category}
				<div
					class="rounded-lg border border-gray-800 bg-gray-900/30 p-6 shadow-lg backdrop-blur-sm"
				>
					<div class="mb-6 flex items-center">
						<svelte:component this={category.icon} class="mr-3 h-5 w-5 text-cyan-400" />
						<h3 class="text-xl font-bold text-white">{category.name}</h3>
					</div>
					<div class="grid grid-cols-2 gap-3">
						{#each category.skills as skill}
							<div
								class="rounded-md bg-gray-800/50 px-3 py-2 text-center text-sm text-gray-200 backdrop-blur-sm
                                transition-all duration-300 hover:-translate-y-1 hover:transform hover:bg-gray-700/70 hover:text-cyan-300 hover:shadow-md"
							>
								<div class="flex items-center justify-center">
									<i class="{skill.icon} mr-2 text-lg" aria-hidden="true"></i>
									<span>{skill.name}</span>
								</div>
							</div>
						{/each}
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
