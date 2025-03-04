<script>
	import { Header, Hero, About, Services, Contact, SubmissionForm, Footer } from '$components';
</script>

<main class="relative min-h-screen bg-gradient-to-b from-slate-900 via-blue-900 to-slate-900">
	<!-- Background Elements -->
	<div class="absolute inset-0 overflow-hidden">
		<div class="absolute inset-0 bg-[url('/grid.svg')] opacity-20"></div>
		<div
			class="absolute -top-40 -right-40 h-[500px] w-[500px] rounded-full bg-blue-500/10 blur-3xl"
		></div>
		<div
			class="absolute -bottom-40 -left-40 h-[500px] w-[500px] rounded-full bg-cyan-500/10 blur-3xl"
		></div>
	</div>
	<Header />
	<Hero />
	<About />
	<Services />
	<Contact />
	<!-- <SubmissionForm /> -->
	<Footer />
</main>
