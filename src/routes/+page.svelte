<script lang="ts">
	import { Github, Linkedin, Twitter, ArrowDown } from '@lucide/svelte';
	import About from '$lib/components/About.svelte';
	import Projects from '$lib/components/Projects.svelte';
	import Skills from '$lib/components/Skills.svelte';
	import Contact from '$lib/components/Contact.svelte';
</script>

<svelte:head>
	<title>Kyle Mendell</title>
	<meta name="description" content="Web developer specializing in modern web applications" />
</svelte:head>

<main>
	<!-- Hero Section - Simplified -->
	<section class="flex min-h-screen flex-col items-center justify-center px-4 text-center">
		<h1 class="mb-4 text-5xl font-bold md:text-6xl">
			Hi, I'm <span class="text-cyan-400">Kyle Mendell</span>
		</h1>

		<p class="mb-8 max-w-lg text-xl text-gray-300">
			Support Engineer & Open Source developer focused on building unique and functional software.
		</p>

		<div class="mb-12 flex space-x-8">
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

		<a
			href="#about"
			class="flex animate-bounce items-center justify-center text-gray-400 transition-colors hover:text-cyan-400"
		>
			<ArrowDown class="h-8 w-8" />
			<span class="sr-only">Scroll down</span>
		</a>
	</section>

	<!-- Other Sections -->
	<About />
	<Projects />
	<Skills />
	<Contact />
</main>
