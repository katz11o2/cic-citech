<script>
	import { CIT, CHOSS, CIC, IISC } from '$lib';
	import { onMount } from 'svelte';
	import { fade, slide } from 'svelte/transition';

	let isMenuOpen = false;
	let scrollY = 0;

	const logos = [
		{ src: CIT, alt: 'CIT', class: 'h-16' },
		{ src: CHOSS, alt: 'CHOSS', class: 'h-14' },
		{ src: CIC, alt: 'CIC', class: 'h-14' },
		{ src: IISC, alt: 'IISc', class: 'h-14' }
	];

	const navLinks = [
		{ href: '#about', text: 'About' },
		{ href: '#services', text: 'Services' },
		{ href: '#programs', text: 'Programs' },
		{ href: '#contact', text: 'Teacher' },
		{ href: '#news', text: 'News' },
		{ href: '#careers', text: 'Careers' }
	];

	$: isScrolled = scrollY > 50;
	$: isCompact = scrollY > 100;

	const toggleMenu = () => (isMenuOpen = !isMenuOpen);

	let currentNewsIndex = 0;
	const news = [
		'Cambridge Institute named Top Innovation Hub 2024',
		'New Industry Partnership Program Launched',
		'Student Startups Raised $5M+ This Quarter',
		'Join Our Next Innovation Workshop'
	];

	onMount(() => {
		const newsInterval = setInterval(() => {
			currentNewsIndex = (currentNewsIndex + 1) % news.length;
		}, 4000);

		return () => clearInterval(newsInterval);
	});

	onMount(() => {
		const handleResize = () => {
			if (window.innerWidth >= 768) isMenuOpen = false;
		};
		window.addEventListener('resize', handleResize);
		return () => window.removeEventListener('resize', handleResize);
	});

	// Adjust height based on scroll position
	$: headerHeight = isCompact ? 'h-10' : isScrolled ? 'h-16' : 'h-24';
	$: headerPadding = isCompact ? 'py-0' : isScrolled ? 'py-1' : 'py-2';
</script>

<svelte:window bind:scrollY />

<header
	class="fixed top-0 z-50 w-full transition-all duration-300 {headerPadding} {isScrolled
		? 'bg-slate-900/95 backdrop-blur-sm'
		: 'bg-transparent'} "
>
	<div class="container mx-auto px-6">
		<!-- Mobile Header -->
		<div class="flex items-center justify-between md:hidden">
			<img src={CIT} alt="CIT" class="h-12 w-auto" />
			<button
				on:click={toggleMenu}
				class="rounded-lg p-2.5 text-white transition-colors hover:bg-white/10"
				aria-label="Toggle menu"
			>
				<svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					{#if isMenuOpen}
						<path stroke-linecap="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
					{:else}
						<path stroke-linecap="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
					{/if}
				</svg>
			</button>
		</div>

		<!-- Desktop Navigation -->
		<div class="hidden md:block">
			<div
				class="flex items-center justify-between transition-all duration-300 {isCompact
					? 'py-0'
					: 'py-1'}"
			>
				<div
					class="flex items-center space-x-6 transition-all duration-300"
					class:opacity-0={isCompact}
					class:invisible={isCompact}
				>
					{#each logos.slice(0, 2) as logo}
						<img
							src={logo.src}
							alt={logo.alt}
							class="{logo.class} w-auto transition-transform hover:scale-105"
						/>
					{/each}
				</div>
				<div
					class="text-center transition-all duration-300 {isCompact
						? '-translate-y-0.5 transform'
						: ''}"
				>
					<h1
						class="text-lg font-bold text-white transition-all duration-300 {isCompact
							? 'text-base'
							: 'text-xl'}"
					>
						Industry Academia Smart Initiative
					</h1>
					<p class="text-xs text-blue-200 transition-all duration-300" class:opacity-0={isCompact}>
						Innovate • Incubate • Impact
					</p>
				</div>
				<div
					class="flex items-center space-x-6 transition-all duration-300"
					class:opacity-0={isCompact}
					class:invisible={isCompact}
				>
					{#each logos.slice(2) as logo}
						<img
							src={logo.src}
							alt={logo.alt}
							class="{logo.class} w-auto transition-transform hover:scale-105"
						/>
					{/each}
				</div>
			</div>

			<nav
				class="flex justify-center space-x-12 transition-all duration-300 {isCompact
					? 'mt-0'
					: 'mt-2'}"
			>
				{#each navLinks as { href, text }}
					<a
						{href}
						class="group relative text-sm font-medium text-blue-100 transition-colors hover:text-white"
					>
						{text}
						<span
							class="absolute -bottom-1 left-0 h-0.5 w-0 bg-blue-400 transition-all group-hover:w-full"
						></span>
					</a>
				{/each}
			</nav>
		</div>

		<!-- News Ticker -->
		<div
			class="container mx-auto mt-4 flex w-fit flex-col items-center justify-center gap-2 px-6 transition-all
				duration-300"
		>
			<div class="flex w-fit items-center text-blue-100">
				<span
					class="mr-4 rounded bg-blue-500 px-2 py-0.5 text-xs font-semibold tracking-wider uppercase"
				>
					Latest
				</span>
				<p class="text-sm transition-all duration-500" in:fade={{ duration: 300 }}>
					{news[currentNewsIndex]}
				</p>
			</div>
		</div>

		<!-- Mobile Menu -->
		{#if isMenuOpen}
			<div
				class="absolute top-full right-0 left-0 border-t border-white/10 bg-slate-900/95 shadow-lg backdrop-blur-sm"
				transition:slide={{ duration: 300 }}
			>
				<nav class="divide-y divide-white/10">
					{#each navLinks as { href, text }}
						<a
							{href}
							class="block px-6 py-3 text-blue-100 transition-colors hover:bg-white/5 hover:text-white"
							on:click={toggleMenu}
						>
							{text}
						</a>
					{/each}
				</nav>
				<div class="grid grid-cols-2 gap-6 bg-slate-800/50 p-6">
					{#each logos as logo}
						<img src={logo.src} alt={logo.alt} class="mx-auto h-12 w-auto" />
					{/each}
				</div>
			</div>
		{/if}
	</div>
</header>

<div class="{headerHeight} transition-all duration-300"></div>

<style>
	header {
		box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
	}

	nav a {
		-webkit-tap-highlight-color: transparent;
	}

	p {
		min-width: 300px;
	}

	.invisible {
		visibility: hidden;
		pointer-events: none;
	}
</style>
