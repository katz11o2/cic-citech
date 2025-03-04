<script>
	import { fly, fade } from 'svelte/transition';
	import { onMount } from 'svelte';

	let isVisible = false;

	onMount(() => {
		isVisible = true;
	});

	const services = [
		{
			title: 'Industry Problem Solving',
			description:
				'Transform complex business challenges into opportunities with our cutting-edge technological solutions and expert guidance.',
			icon: '🎯',
			highlight: 'Custom Solutions',
			features: ['Rapid Prototyping', 'Expert Consultation', 'Industry-Specific Solutions']
		},
		{
			title: 'R&D Partnership',
			description:
				'Access world-class research facilities and collaborate with leading experts to drive innovation in your field.',
			icon: '🔬',
			highlight: 'Advanced Labs',
			features: ['State-of-art Labs', 'Research Expertise', 'Innovation Support']
		},
		{
			title: 'Innovation Support',
			description:
				'Get comprehensive support throughout your innovation journey, from initial concept to market success.',
			icon: '💡',
			highlight: 'End-to-End Support',
			features: ['Mentorship', 'Funding Access', 'Market Strategy']
		}
	];
</script>

<section class="relative py-32">
	<!-- Background Elements -->
	<div class="absolute inset-0 bg-gradient-to-br from-slate-900 via-blue-900/50 to-slate-900">
		<div class="absolute inset-0 bg-[url('/grid.svg')] opacity-10"></div>
		<div
			class="absolute left-1/4 h-[600px] w-[600px] rounded-full bg-blue-500/20 blur-[120px]"
		></div>
		<div
			class="absolute top-1/2 right-1/4 h-[600px] w-[600px] rounded-full bg-cyan-500/20 blur-[120px]"
		></div>
	</div>

	<div class="relative container mx-auto px-6">
		<!-- Header -->
		{#if isVisible}
			<div class="mb-20" in:fly={{ y: 50, duration: 1000 }}>
				<div class="flex flex-col items-center text-center">
					<span
						class="mb-4 inline-block rounded-full bg-blue-500/10 px-6 py-2 text-sm font-semibold text-blue-300"
					>
						Our Services
					</span>
					<h2 class="mb-6 text-4xl font-bold text-white lg:text-6xl">
						Transform Your Ideas Into
						<span
							class="mt-2 block bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent"
						>
							Innovation Reality
						</span>
					</h2>
					<p class="max-w-2xl text-lg text-blue-200/90">
						Partner with us to access world-class resources, expert guidance, and comprehensive
						support to bring your innovations to life.
					</p>
				</div>
			</div>
		{/if}

		<!-- Services Grid -->
		{#if isVisible}
			<div class="grid gap-8 lg:grid-cols-3" in:fly={{ y: 50, duration: 1000, delay: 200 }}>
				{#each services as service, i}
					<div class="group relative" in:fly={{ x: 50, duration: 800, delay: 300 + i * 100 }}>
						<div
							class="relative h-full overflow-hidden rounded-2xl border border-white/10 bg-white/5 p-8 backdrop-blur-sm transition-all duration-500 hover:-translate-y-2 hover:border-blue-500/30"
						>
							<!-- Icon -->
							<div
								class="mb-6 inline-block rounded-xl bg-gradient-to-br from-blue-500/20 to-cyan-500/20 p-4 text-4xl ring-1 ring-white/10"
							>
								{service.icon}
							</div>

							<!-- Content -->
							<h3 class="mb-4 text-2xl font-bold text-white">
								{service.title}
							</h3>
							<p class="mb-8 text-blue-200/90">
								{service.description}
							</p>

							<!-- Features List -->
							<ul class="mb-8 space-y-3">
								{#each service.features as feature}
									<li class="flex items-center text-sm text-blue-200/80">
										<svg class="mr-2 h-4 w-4 text-blue-400" viewBox="0 0 20 20" fill="currentColor">
											<path
												d="M10 18a8 8 0 100-16 8 8 0 000 16zm3.707-9.293a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
											/>
										</svg>
										{feature}
									</li>
								{/each}
							</ul>

							<!-- Footer -->
							<div class="flex items-center justify-between">
								<span
									class="rounded-full bg-gradient-to-r from-blue-500/10 to-cyan-500/10 px-4 py-1.5 text-sm font-medium text-blue-300 ring-1 ring-blue-400/20"
								>
									{service.highlight}
								</span>

								<button
									class="group/btn inline-flex items-center space-x-2 rounded-lg px-4 py-2 text-blue-400 transition-colors hover:bg-blue-500/10"
								>
									<span class="text-sm font-medium">Learn More</span>
									<svg
										class="h-4 w-4 transition-transform duration-300 group-hover/btn:translate-x-1"
										fill="none"
										stroke="currentColor"
										viewBox="0 0 24 24"
									>
										<path
											stroke-linecap="round"
											stroke-linejoin="round"
											stroke-width="2"
											d="M13 7l5 5m0 0l-5 5m5-5H6"
										/>
									</svg>
								</button>
							</div>

							<!-- Hover Effect -->
							<div
								class="absolute inset-0 -z-10 bg-gradient-to-br from-blue-500/0 via-blue-500/5 to-cyan-500/0 opacity-0 transition-opacity duration-500 group-hover:opacity-100"
							></div>
						</div>
					</div>
				{/each}
			</div>
		{/if}
	</div>
</section>

<style>
	section {
		min-height: 100vh;
		perspective: 1000px;
	}
</style>
