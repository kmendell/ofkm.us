<script lang="ts">
	import { onMount } from 'svelte';
	import { Menu, X } from '@lucide/svelte';

	let scrolled = false;
	let mobileMenuOpen = false;

	onMount(() => {
		const handleScroll = () => {
			scrolled = window.scrollY > 20;
		};

		window.addEventListener('scroll', handleScroll);
		return () => window.removeEventListener('scroll', handleScroll);
	});

	const toggleMobileMenu = () => {
		mobileMenuOpen = !mobileMenuOpen;
	};

	const closeMobileMenu = () => {
		mobileMenuOpen = false;
	};
</script>

<header
	class={`fixed top-0 z-50 w-full transition-all duration-300 ${
		scrolled ? 'bg-gray-900/90 shadow-md backdrop-blur-sm' : 'bg-transparent'
	}`}
>
	<div class="container mx-auto flex items-center justify-between px-6 py-4">
		<a href="/" class="text-xl font-bold text-white">KM</a>

		<nav class="hidden md:block">
			<ul class="flex space-x-8 text-gray-200">
				<li><a href="#about" class="transition-colors hover:text-cyan-400">About</a></li>
				<li><a href="#projects" class="transition-colors hover:text-cyan-400">Projects</a></li>
				<li><a href="#skills" class="transition-colors hover:text-cyan-400">Skills</a></li>
				<li><a href="#contact" class="transition-colors hover:text-cyan-400">Contact</a></li>
			</ul>
		</nav>

		<!-- Mobile menu button -->
		<button
			class="text-white focus:outline-none md:hidden"
			aria-label="Toggle menu"
			on:click={toggleMobileMenu}
		>
			{#if mobileMenuOpen}
				<X class="h-6 w-6" />
			{:else}
				<Menu class="h-6 w-6" />
			{/if}
		</button>
	</div>

	<!-- Mobile menu -->
	{#if mobileMenuOpen}
		<div class="bg-gray-900/95 backdrop-blur-md md:hidden">
			<nav class="container mx-auto px-6 py-4">
				<ul class="space-y-4 text-gray-200">
					<li>
						<a
							href="#about"
							class="block py-2 transition-colors hover:text-cyan-400"
							on:click={closeMobileMenu}
						>
							About
						</a>
					</li>
					<li>
						<a
							href="#projects"
							class="block py-2 transition-colors hover:text-cyan-400"
							on:click={closeMobileMenu}
						>
							Projects
						</a>
					</li>
					<li>
						<a
							href="#skills"
							class="block py-2 transition-colors hover:text-cyan-400"
							on:click={closeMobileMenu}
						>
							Skills
						</a>
					</li>
					<li>
						<a
							href="#contact"
							class="block py-2 transition-colors hover:text-cyan-400"
							on:click={closeMobileMenu}
						>
							Contact
						</a>
					</li>
				</ul>
			</nav>
		</div>
	{/if}
</header>
