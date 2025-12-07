<script lang="ts">
	import { Monitor, Server, Wrench } from '@lucide/svelte';
	import { Motion } from 'svelte-motion';

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

	const containerVariants = {
		hidden: { opacity: 0 },
		visible: {
			opacity: 1,
			transition: {
				staggerChildren: 0.2
			}
		}
	};

	const itemVariants = {
		hidden: { y: 20, opacity: 0 },
		visible: {
			y: 0,
			opacity: 1,
			transition: {
				duration: 0.5
			}
		}
	};
</script>

<section id="skills" class="py-20 relative overflow-hidden">
	<!-- Background glow -->
	<div class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[500px] h-[500px] bg-primary-500/10 blur-[200px] rounded-full pointer-events-none"></div>

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
				<h2 class="mb-3 text-center text-3xl font-bold text-white">Skills & Expertise</h2>
				<p class="mx-auto mb-12 max-w-2xl text-center text-gray-400">
					Here's an overview of my technical skills and areas of expertise.
				</p>
			</div>
		</Motion>

		<Motion
			variants={containerVariants}
			{...{
				initial: "hidden",
				whileInView: "visible",
				viewport: { once: true }
			}}
			let:motion
		>
			<div use:motion class="grid gap-8 md:grid-cols-3">
				{#each skillCategories as category}
					<Motion variants={itemVariants} let:motion>
						<div
							use:motion
							class="group relative rounded-xl border border-white/10 bg-black/40 p-6 backdrop-blur-md transition-all duration-300 hover:border-primary-500/50 hover:shadow-[0_0_30px_-10px_rgba(14,165,233,0.3)]"
						>
							<div class="absolute inset-0 bg-linear-to-br from-primary-500/5 to-transparent opacity-0 transition-opacity duration-300 group-hover:opacity-100 rounded-xl"></div>
							
							<div class="relative z-10">
								<div class="mb-6 flex items-center">
									<div class="p-3 rounded-lg bg-primary-500/10 text-primary-400 mr-4 group-hover:scale-110 transition-transform duration-300">
										<category.icon class="h-6 w-6" />
									</div>
									<h3 class="text-xl font-bold text-white group-hover:text-primary-400 transition-colors">{category.name}</h3>
								</div>
								<div class="grid grid-cols-2 gap-3">
									{#each category.skills as skill}
										<div
											class="flex items-center justify-center rounded-lg border border-white/5 bg-white/5 px-3 py-2.5 text-center text-sm text-gray-300 transition-all duration-300 hover:bg-white/10 hover:text-white hover:border-primary-500/30"
										>
											<i class="{skill.icon} mr-2 text-lg" aria-hidden="true"></i>
											<span>{skill.name}</span>
										</div>
									{/each}
								</div>
							</div>
						</div>
					</Motion>
				{/each}
			</div>
		</Motion>
	</div>
</section>
