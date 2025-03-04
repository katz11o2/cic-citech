<script>
    import { onMount } from 'svelte';

    const slides = [
        {
            image: '/images/innovation-lab.jpg',
            title: 'Innovation Lab',
            description: 'State-of-the-art facilities driving breakthrough innovations',
            stats: { value: '100+', label: 'Projects Completed' }
        },
        {
            image: '/images/research-center.jpg',
            title: 'Research Excellence',
            description: 'Advanced research capabilities and expert collaboration',
            stats: { value: '50+', label: 'Industry Partners' }
        },
        {
            image: '/images/global-network.jpg',
            title: 'Global Network',
            description: 'Worldwide ecosystem of innovators and industry leaders',
            stats: { value: '25+', label: 'Countries' }
        }
    ];

    let currentSlide = 0;
    let autoplayInterval;

    const nextSlide = () => {
        currentSlide = (currentSlide + 1) % slides.length;
    };

    const prevSlide = () => {
        currentSlide = (currentSlide - 1 + slides.length) % slides.length;
    };

    onMount(() => {
        autoplayInterval = setInterval(nextSlide, 5000);
        return () => clearInterval(autoplayInterval);
    });
</script>

<section class="relative
">
    <!-- Slider Container -->
    <div class="relative container px-5 bg-white mx-auto h-[600px] overflow-hidden">
        <!-- Slides -->
        {#each slides as slide, i}
            <div
                class="absolute w-full inset-0 transition-opacity duration-700"
                class:opacity-100={i === currentSlide}
                class:opacity-0={i !== currentSlide}
            >
                <!-- Image with Overlay -->
                <div class="relative h-full">
                    <img src={slide.image} alt={slide.title} class="h-full w-full object-cover" />
                    <div class="absolute inset-0 bg-gradient-to-r from-blue-900/90 to-cyan-900/50"></div>
                </div>

                <!-- Content -->
                <div class="absolute inset-0">
                    <div class="container mx-auto h-full px-6">
                        <div class="flex h-full items-center">
                            <div class="max-w-2xl">
                                <h2 class="text-4xl font-bold text-blue-100 lg:text-5xl">
                                    {slide.title}
                                </h2>
                                <p class="mt-4 text-xl text-blue-200">
                                    {slide.description}
                                </p>
                                <div class="mt-8 flex items-center space-x-4">
                                    <div class="rounded-lg bg-white/5 px-6 py-4 backdrop-blur-sm">
                                        <p class="text-3xl font-bold text-white">{slide.stats.value}</p>
                                        <p class="text-sm text-blue-200">{slide.stats.label}</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        {/each}

        <!-- Navigation Buttons -->
        <div class="absolute inset-0 flex items-center justify-between px-4">
            <button
                on:click={prevSlide}
                class="rounded-full bg-blue-500/10 p-3 text-blue-100 backdrop-blur-sm transition-all hover:bg-blue-500/20"
            >
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M15 19l-7-7 7-7"
                    />
                </svg>
            </button>
            <button
                on:click={nextSlide}
                class="rounded-full bg-blue-500/10 p-3 text-blue-100 backdrop-blur-sm transition-all hover:bg-blue-500/20"
            >
                <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                </svg>
            </button>
        </div>

        <!-- Slide Indicators -->
        <div class="absolute right-0 bottom-6 left-0">
            <div class="flex justify-center space-x-2">
                {#each slides as _, i}
                    <button
                        on:click={() => (currentSlide = i)}
                        class={`h-2 w-8 rounded-full transition-all ${
                            i === currentSlide ? 'bg-cyan-400' : 'bg-blue-800/50'
                        }`}
                    ></button>
                {/each}
            </div>
        </div>
    </div>
</section>
