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
	const contactInfo = {
		industry: {
			name: 'Dr. Jane Smith',
			role: 'Head of Industry Relations',
			email: 'industry@cambridgeinstitute.edu',
			phone: '+1 (555) 123-4567'
		},
		center: {
			name: 'Cambridge Institute Innovation Center',
			address: ['5th Floor, Innovation Hub', '123 Innovation Street', 'Cambridge, MA 02138'],
			hours: 'Monday - Friday, 9:00 AM - 5:00 PM'
		}
	};
</script>

<section class="relative py-32">
	<!-- Background Elements -->
	<div class="absolute inset-0 opacity-20">
		<div class="absolute left-1/4 h-96 w-96 rounded-full bg-blue-500/30 blur-[100px]"></div>
		<div
			class="absolute top-1/2 right-1/4 h-96 w-96 rounded-full bg-cyan-500/30 blur-[100px]"
		></div>
	</div>

	<div class="relative container mx-auto px-6">
		<!-- Header -->
		<div class="mb-16 text-center">
			<span
				class="mb-4 inline-block rounded-lg bg-white/5 px-4 py-1.5 text-sm font-medium text-blue-200 backdrop-blur-sm"
			>
				Connect With Us
			</span>
			<h2 class="mb-6 text-4xl font-bold text-white lg:text-5xl xl:text-6xl">
				Let's Build The
				<span class="bg-gradient-to-r from-blue-400 to-cyan-400 bg-clip-text text-transparent">
					Future Together
				</span>
			</h2>
			<p class="mx-auto max-w-2xl text-lg text-blue-100 lg:text-xl">
				Whether you're looking to collaborate or have an innovative idea, we're here to help
			</p>
		</div>

		<div class="grid gap-8 lg:grid-cols-5">
			<!-- Contact Information Column -->
			<div class="space-y-8 lg:col-span-2">
				<!-- Industry Relations Card -->
				<div
					class="group rounded-xl bg-white/5 p-8 backdrop-blur-sm transition-all hover:bg-white/10"
				>
					<h3 class="mb-6 text-2xl font-bold text-white">Contact Us</h3>
					<div class="space-y-6">
						<div class="space-y-4">
							<p class="text-xl font-semibold text-white">{contactInfo.industry.name}</p>
							<p class="text-blue-200">{contactInfo.industry.role}</p>
							<div class="space-y-3">
								<a
									href={`mailto:${contactInfo.industry.email}`}
									class="flex items-center gap-3 text-blue-200 transition-colors hover:text-blue-400"
								>
									<svg class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
										<path
											d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"
										/>
									</svg>
									{contactInfo.industry.email}
								</a>
								<a
									href={`tel:${contactInfo.industry.phone}`}
									class="flex items-center gap-3 text-blue-200 transition-colors hover:text-blue-400"
								>
									<svg class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
										<path
											d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z"
										/>
									</svg>
									{contactInfo.industry.phone}
								</a>
							</div>
						</div>
					</div>
				</div>

				<!-- Address Card -->
				<div
					class="group rounded-xl bg-white/5 p-8 backdrop-blur-sm transition-all hover:bg-white/10"
				>
					<h3 class="mb-6 text-2xl font-bold text-white">Visit Us</h3>
					<div class="space-y-6">
						<div class="space-y-4">
							{#each contactInfo.center.address as line}
								<p class="text-blue-200">{line}</p>
							{/each}
							<div class="flex items-center gap-3 text-blue-200">
								<svg
									class="h-5 w-5 text-blue-400"
									fill="none"
									viewBox="0 0 24 24"
									stroke="currentColor"
								>
									<path d="M12 6v6h4.5m4.5 0a9 9 0 11-18 0 9 9 0 0118 0z" />
								</svg>
								{contactInfo.center.hours}
							</div>
						</div>
						<button
							class="flex items-center gap-2 rounded-lg border border-blue-400/30 px-4 py-2 text-blue-100 transition-all hover:bg-white/10"
						>
							View on Map
							<svg
								class="h-4 w-4"
								viewBox="0 0 24 24"
								fill="none"
								stroke="currentColor"
								stroke-width="2"
							>
								<path d="M7 17L17 7M17 7H7M17 7V17" />
							</svg>
						</button>
					</div>
				</div>
			</div>

			<!-- Submission Form Column -->
			<div class="lg:col-span-3">
				<form
					on:submit|preventDefault={handleSubmit}
					class="mx-auto max-w-3xl rounded-xl bg-white/5 p-8 backdrop-blur-sm"
				>
					<div class="mb-8 grid gap-6 md:grid-cols-2">
						<div class="space-y-2">
							<label for="companyName" class="text-sm font-medium text-blue-200">Company Name</label
							>
							<input
								type="text"
								id="companyName"
								bind:value={formData.companyName}
								required
								class="w-full rounded-lg border border-blue-400/30 bg-white/5 px-4 py-3 text-white backdrop-blur-sm placeholder:text-blue-200/50 focus:border-blue-400 focus:ring-1 focus:ring-blue-400 focus:outline-none"
								placeholder="Your company name"
							/>
						</div>
						<div class="space-y-2">
							<label for="contactName" class="text-sm font-medium text-blue-200">Contact Name</label
							>
							<input
								type="text"
								id="contactName"
								bind:value={formData.contactName}
								required
								class="w-full rounded-lg border border-blue-400/30 bg-white/5 px-4 py-3 text-white backdrop-blur-sm placeholder:text-blue-200/50 focus:border-blue-400 focus:ring-1 focus:ring-blue-400 focus:outline-none"
								placeholder="Your full name"
							/>
						</div>
						<div class="space-y-2">
							<label for="email" class="text-sm font-medium text-blue-200">Email</label>
							<input
								type="email"
								id="email"
								bind:value={formData.email}
								required
								class="w-full rounded-lg border border-blue-400/30 bg-white/5 px-4 py-3 text-white backdrop-blur-sm placeholder:text-blue-200/50 focus:border-blue-400 focus:ring-1 focus:ring-blue-400 focus:outline-none"
								placeholder="your@email.com"
							/>
						</div>
						<div class="space-y-2">
							<label for="phone" class="text-sm font-medium text-blue-200">Phone</label>
							<input
								type="tel"
								id="phone"
								bind:value={formData.phone}
								class="w-full rounded-lg border border-blue-400/30 bg-white/5 px-4 py-3 text-white backdrop-blur-sm placeholder:text-blue-200/50 focus:border-blue-400 focus:ring-1 focus:ring-blue-400 focus:outline-none"
								placeholder="+1 (555) 000-0000"
							/>
						</div>
					</div>

					<div class="mb-8 space-y-2">
						<label for="industry" class="text-sm font-medium text-blue-200">Industry</label>
						<input
							type="text"
							id="industry"
							bind:value={formData.industry}
							required
							class="w-full rounded-lg border border-blue-400/30 bg-white/5 px-4 py-3 text-white backdrop-blur-sm placeholder:text-blue-200/50 focus:border-blue-400 focus:ring-1 focus:ring-blue-400 focus:outline-none"
							placeholder="e.g., Healthcare, Technology, Manufacturing"
						/>
					</div>

					<div class="mb-8 space-y-2">
						<label class="text-sm font-medium text-blue-200">Submission Type</label>
						<div class="flex gap-6">
							<label class="flex items-center space-x-2">
								<input
									type="radio"
									bind:group={formData.submissionType}
									value="problem"
									class="text-blue-400 focus:ring-blue-400"
								/>
								<span class="text-blue-100">Industry Problem</span>
							</label>
							<label class="flex items-center space-x-2">
								<input
									type="radio"
									bind:group={formData.submissionType}
									value="idea"
									class="text-blue-400 focus:ring-blue-400"
								/>
								<span class="text-blue-100">New Product Idea</span>
							</label>
						</div>
					</div>

					<div class="mb-8 space-y-2">
						<label for="description" class="text-sm font-medium text-blue-200">Description</label>
						<textarea
							id="description"
							bind:value={formData.description}
							required
							rows="5"
							class="w-full rounded-lg border border-blue-400/30 bg-white/5 px-4 py-3 text-white backdrop-blur-sm placeholder:text-blue-200/50 focus:border-blue-400 focus:ring-1 focus:ring-blue-400 focus:outline-none"
							placeholder="Describe your challenge or idea in detail..."
						></textarea>
					</div>

					<button
						type="submit"
						class="group relative w-full rounded-lg bg-blue-500 px-8 py-3 font-semibold text-white transition-all hover:bg-blue-600"
					>
						Submit Proposal
						<span class="absolute -top-1 -right-1 flex h-3 w-3">
							<span
								class="absolute inline-flex h-full w-full animate-ping rounded-full bg-blue-400 opacity-75"
							></span>
							<span class="relative inline-flex h-3 w-3 rounded-full bg-blue-500"></span>
						</span>
					</button>
				</form>
			</div>
		</div>
	</div>
</section>
