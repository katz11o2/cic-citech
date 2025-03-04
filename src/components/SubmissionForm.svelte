<script>
	let formData = {
		companyName: '',
		contactName: '',
		email: '',
		phone: '',
		industry: '',
		submissionType: 'problem',
		description: ''
	};

	function handleSubmit() {
		console.log('Form submitted:', formData);
	}
</script>

<section
	id="submit"
	class="relative  bg-gradient-to-br from-slate-900 via-blue-900 to-slate-900 py-32"
>
	<!-- Background Pattern -->
	<div
		class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNjAiIGhlaWdodD0iNjAiIHZpZXdCb3g9IjAgMCA2MCA2MCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48ZyBmaWxsPSJub25lIiBmaWxsLXJ1bGU9ImV2ZW5vZGQiPjxwYXRoIGQ9Ik0wIDBoNjB2NjBIMHoiLz48cGF0aCBkPSJNMiAyaDJ2MkgyeiIgZmlsbD0icmdiYSgyNTUsMjU1LDI1NSwwLjA1KSIvPjwvZz48L3N2Zz4=')] opacity-20"
	/>

	<!-- Decorative Elements -->
	<div class="absolute top-1/4 left-0 h-96 w-96 rounded-full bg-blue-500/20 blur-3xl"></div>
	<div class="absolute right-0 bottom-1/4 h-96 w-96 rounded-full bg-cyan-500/20 blur-3xl"></div>

	<div class="relative container mx-auto px-6">
		<!-- Header -->
		<div class="mb-16 text-center">
			<span
				class="mb-4 inline-block rounded-lg bg-white/5 px-4 py-1.5 text-sm font-medium text-blue-200 backdrop-blur-sm"
			>
				Submit Your Proposal
			</span>
			<h2 class="mb-6 text-4xl font-bold text-white lg:text-5xl xl:text-6xl">
				Share Your
				<span class="bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent">
					Innovation
				</span>
			</h2>
			<p class="mx-auto max-w-2xl text-lg text-blue-100 lg:text-xl">
				Whether you have an industry challenge or innovative idea, we're here to help bring it to
				life
			</p>
		</div>

		<!-- Form -->
		
	</div>
</section>
