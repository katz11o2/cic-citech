<script>
    const stats = [
        { icon: '🎯', value: '10+', label: 'Years Experience' },
        { icon: '🤝', value: '50+', label: 'Industry Partners' },
        { icon: '⭐', value: '100+', label: 'Success Stories' },
        { icon: '👨‍🏫', value: '25+', label: 'Expert Mentors' }
    ];

    const studentStartups = [
        { name: 'InnovateTech', description: 'AI Solutions', year: '2024', status: 'Active' },
        { name: 'GreenCycle', description: 'Eco-Friendly Products', year: '2023', status: 'Active' },
        { name: 'EduConnect', description: 'Online Learning Platform', year: '2024', status: 'Seed' },
        { name: 'HealthFirst', description: 'Healthcare Innovation', year: '2023', status: 'Series A' }
    ];

    const achievements = [
        { year: '2024', title: 'Innovation Excellence Award' },
        { year: '2023', title: 'Best Incubator Program' },
        { year: '2023', title: 'Top Research Institution' }
    ];

    const facultyAchievements = [
        {
            name: 'Dr. Sarah Johnson',
            title: 'Head of Innovation',
            achievements: [
                'Research Excellence Award 2024',
                'Published in Nature Technology',
                '5 Patents Filed'
            ],
            image: 'https://placehold.co/200x200'
        },
        {
            name: 'Prof. Michael Chen',
            title: 'Lead Research Mentor',
            achievements: [
                'Best Mentor Award 2023',
                'Industry Innovation Prize',
                '10+ Startups Mentored'
            ],
            image: 'https://placehold.co/200x200'
        },
        {
            name: 'Dr. Emily Roberts',
            title: 'Technology Director',
            achievements: [
                'Tech Innovation Award',
                'IEEE Fellow',
                '15+ Research Papers'
            ],
            image: 'https://placehold.co/200x200'
        }
    ];
</script>

<div class="relative min-h-screen bg-gradient-to-br from-slate-50 via-blue-50/75 to-slate-50">
    <!-- Hero Section with Animated Background -->
    <section class="relative overflow-hidden pt-32 pb-20">
        <div class="absolute inset-0 -z-10">
            <div class="absolute inset-0 bg-[linear-gradient(to_right,#80808012_1px,transparent_1px),linear-gradient(to_bottom,#80808012_1px,transparent_1px)] bg-[size:24px_24px]"></div>
            <div class="absolute left-0 top-24 h-72 w-72 rounded-full bg-blue-200 opacity-20 blur-[100px]"></div>
            <div class="absolute right-0 top-96 h-72 w-72 rounded-full bg-cyan-200 opacity-20 blur-[100px]"></div>
        </div>

        <div class="container relative mx-auto px-6">
            <div class="grid items-center gap-12 lg:grid-cols-2">
                <div>
                    <div class="inline-flex items-center rounded-full border border-blue-100 bg-blue-50/50 px-3 py-1">
                        <span class="text-sm font-medium text-blue-800">Innovate • Research • Transform</span>
                    </div>
                    <h1 class="mt-6 text-5xl font-bold tracking-tight text-slate-900 lg:text-6xl xl:text-7xl">
                        Shaping the
                        <span class="relative whitespace-nowrap">
                            <svg aria-hidden="true" viewBox="0 0 418 42" class="absolute left-0 top-2/3 h-[0.58em] w-full fill-cyan-300/70" preserveAspectRatio="none">
                                <path d="M203.371.916c-26.013-2.078-76.686 1.963-124.73 9.946L67.3 12.749C35.421 18.062 18.2 21.766 6.004 25.934 1.244 27.561.828 27.778.874 28.61c.07 1.214.828 1.121 9.595-1.176 9.072-2.377 17.15-3.92 39.246-7.496C123.565 7.986 157.869 4.492 195.942 5.046c7.461.108 19.25 1.696 19.17 2.582-.107 1.183-7.874 4.31-25.75 10.366-21.992 7.45-35.43 12.534-36.701 13.884-2.173 2.308-.202 4.407 4.442 4.734 2.654.187 3.263.157 15.593-.78 35.401-2.686 57.944-3.488 88.365-3.143 46.327.526 75.721 2.23 130.788 7.584 19.787 1.924 20.814 1.98 24.557 1.332l.066-.011c1.201-.203 1.53-1.825.399-2.335-2.911-1.31-4.893-1.604-22.048-3.261-57.509-5.556-87.871-7.36-132.059-7.842-23.239-.254-33.617-.116-50.627.674-11.629.54-42.371 2.494-46.696 2.967-2.359.259 8.133-3.625 26.504-9.81 23.239-7.825 27.934-10.149 28.304-14.005.417-4.348-3.529-6-16.878-7.066Z"></path>
                            </svg>
                            <span class="relative">Future</span>
                        </span>
                        <span class="block bg-gradient-to-r from-blue-600 to-cyan-600 bg-clip-text text-transparent">
                            Through Innovation
                        </span>
                    </h1>
                    <p class="mt-8 text-lg leading-relaxed text-slate-600">
                        Where groundbreaking ideas meet world-class expertise. Join us in shaping tomorrow's technology and innovations.
                    </p>
                    <div class="mt-10 flex flex-wrap gap-4">
                        <button class="group relative overflow-hidden rounded-lg bg-slate-900 px-8 py-3 transition-all hover:ring-2 hover:ring-blue-400 hover:ring-offset-2">
                            <span class="relative z-10 font-medium text-white">Explore Programs</span>
                            <div class="absolute inset-0 -z-10 bg-gradient-to-r from-blue-600 to-cyan-600 opacity-0 transition-opacity group-hover:opacity-100"></div>
                        </button>
                        <button class="group rounded-lg border-2 border-slate-200 px-8 py-3 font-medium text-slate-600 transition-all hover:border-blue-400 hover:bg-blue-50">
                            Meet Our Faculty
                        </button>
                    </div>
                </div>
                <div class="relative grid grid-cols-2 gap-4 lg:mt-0">
                    {#each stats as stat}
                        <div class="group rounded-2xl border border-slate-100 bg-white/80 p-6 shadow-sm backdrop-blur-sm transition-all hover:-translate-y-1 hover:shadow-md">
                            <div class="mb-3 inline-block rounded-lg bg-blue-50 p-3 text-2xl">
                                {stat.icon}
                            </div>
                            <p class="text-3xl font-bold text-slate-800">{stat.value}</p>
                            <p class="mt-1 text-sm text-slate-500">{stat.label}</p>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </section>

    <!-- Faculty Section -->
    <section class="relative py-12 bg-gradient-to-b from-transparent via-blue-50/50 to-transparent">
        <div class="container mx-auto px-6">
            <div class="mb-16">
                <span class="mb-4 inline-block rounded-full bg-blue-100 px-3 py-1 text-sm font-medium text-blue-800">
                    Faculty Excellence
                </span>
                <h2 class="text-4xl font-bold text-slate-900">Meet Our Distinguished Faculty</h2>
            </div>
            <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-3">
                {#each facultyAchievements as faculty}
                    <div class="group relative rounded-2xl border border-slate-100 bg-white p-6 shadow-sm transition-all hover:-translate-y-1 hover:shadow-lg">
                        <div class="flex items-center gap-4">
                            <img 
                                src={faculty.image} 
                                alt={faculty.name}
                                class="h-20 w-20 rounded-2xl object-cover shadow-sm transition-transform group-hover:scale-105"
                            />
                            <div>
                                <h3 class="text-xl font-semibold text-slate-900">{faculty.name}</h3>
                                <p class="text-blue-600">{faculty.title}</p>
                            </div>
                        </div>
                        <div class="mt-6 space-y-2">
                            {#each faculty.achievements as achievement}
                                <div class="flex items-center gap-2 rounded-lg bg-slate-50 px-3 py-2 text-sm text-slate-600">
                                    <svg class="h-4 w-4 text-blue-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                                    </svg>
                                    {achievement}
                                </div>
                            {/each}
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </section>

    <!-- Startups Grid -->
    <section class="relative py-12">
        <div class="container mx-auto px-6">
            <div class="mb-16">
                <span class="mb-4 inline-block rounded-full bg-blue-100 px-3 py-1 text-sm font-medium text-blue-800">
                    Success Stories
                </span>
                <h2 class="text-4xl font-bold text-slate-900">Student Startups</h2>
            </div>
            <div class="grid gap-6 lg:grid-cols-2">
                {#each studentStartups as startup}
                    <div class="group relative overflow-hidden rounded-2xl border border-slate-100 bg-white p-8 shadow-sm transition-all hover:-translate-y-1 hover:shadow-lg">
                        <div class="flex items-start justify-between">
                            <div>
                                <h3 class="text-xl font-semibold text-slate-900">{startup.name}</h3>
                                <p class="mt-2 text-slate-600">{startup.description}</p>
                            </div>
                            <div class="flex flex-col items-end gap-2">
                                <span class="inline-flex items-center rounded-full bg-blue-50 px-3 py-1 text-sm font-medium text-blue-700">
                                    {startup.status}
                                </span>
                                <span class="text-sm text-slate-500">{startup.year}</span>
                            </div>
                        </div>
                        <div class="absolute bottom-0 left-0 h-1 w-0 bg-gradient-to-r from-blue-500 to-cyan-500 transition-all duration-300 group-hover:w-full"></div>
                    </div>
                {/each}
            </div>
        </div>
    </section>
</div>