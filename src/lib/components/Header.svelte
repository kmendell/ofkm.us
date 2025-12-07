<script lang="ts">
	import { onMount } from 'svelte';
	import { Menu, X } from '@lucide/svelte';

	let scrolled = $state(false);
	let mobileMenuOpen = $state(false);

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
	class={`fixed z-50 transition-all duration-300 ${
		scrolled
			? 'top-4 left-1/2 w-[95%] max-w-5xl -translate-x-1/2 rounded-full border border-white/10 bg-black/50 shadow-lg backdrop-blur-md md:w-[80%]'
			: 'top-0 left-0 w-full border-b border-transparent bg-transparent'
	}`}
>
	<div class="container mx-auto flex items-center justify-between px-6 py-4">
		<a href="/" class="text-xl font-bold text-white">KM</a>

		<nav class="hidden md:block">
			<ul class="flex space-x-8 text-gray-200">
				<li><a href="#about" class="transition-colors hover:text-primary-400">About</a></li>
				<li><a href="#projects" class="transition-colors hover:text-primary-400">Projects</a></li>
				<li><a href="#skills" class="transition-colors hover:text-primary-400">Skills</a></li>
				<li><a href="#contact" class="transition-colors hover:text-primary-400">Contact</a></li>
			</ul>
		</nav>

		<!-- Mobile menu button -->
		<button
			class="text-white focus:outline-none md:hidden"
			aria-label="Toggle menu"
			onclick={toggleMobileMenu}
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
		<div class="bg-black/90 backdrop-blur-xl md:hidden border-b border-white/10">
			<nav class="container mx-auto px-6 py-4">
				<ul class="space-y-4 text-gray-200">
					<li>
						<a
							href="#about"
							class="block py-2 transition-colors hover:text-primary-400"
							onclick={closeMobileMenu}
						>
							About
						</a>
					</li>
					<li>
						<a
							href="#projects"
							class="block py-2 transition-colors hover:text-primary-400"
							onclick={closeMobileMenu}
						>
							Projects
						</a>
					</li>
					<li>
						<a
							href="#skills"
							class="block py-2 transition-colors hover:text-primary-400"
							onclick={closeMobileMenu}
						>
							Skills
						</a>
					</li>
					<li>
						<a
							href="#contact"
							class="block py-2 transition-colors hover:text-primary-400"
							onclick={closeMobileMenu}
						>
							Contact
						</a>
					</li>
				</ul>
			</nav>
		</div>
	{/if}
</header>
