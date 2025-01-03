<!-- components/LinksProfile.vue -->
<template>
	<div
		class="min-h-screen bg-gradient-to-br from-slate-800 via-slate-900 to-black"
	>
		<div
			class="container mx-auto px-4 py-16 min-h-screen flex items-center justify-center"
		>
			<div
				class="w-full max-w-2xl backdrop-blur-lg bg-white/5 rounded-3xl p-8 shadow-2xl"
			>
				<div class="flex flex-col items-center space-y-8">
					<!-- Profile Section -->
					<div class="relative group">
						<div
							class="absolute -inset-0.5 bg-gradient-to-r from-madblue to-purple-200 rounded-full opacity-75 group-hover:opacity-100 transition duration-500 blur"
						></div>
						<NuxtLink class="relative block">
							<img
								:src="profile.avatar"
								:alt="profile.name"
								class="w-40 h-40 rounded-full object-contain ring-4 ring-white/10 group-hover:ring-white/20 transition duration-300"
							/>
						</NuxtLink>
					</div>

					<div class="text-center space-y-3">
						<h2
							class="text-2xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-pink-500 to-violet-500"
						>
							{{ profile.name }}
						</h2>
						<p class="text-gray-300 text-lg">{{ profile.bio }}</p>
					</div>

					<!-- Social Links -->
					<div class="w-full space-y-4 mt-8">
						<Social
							v-for="link in socialLinks"
							:key="link.id"
							:href="link.url"
							:icon="link.icon"
							:label="link.label"
						/>
					</div>

					<!-- Footer -->
					<div class="pt-8 text-center">
						<p class="text-sm text-gray-400">
							© {{ new Date().getFullYear() }} {{ profile.name }}
						</p>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
// Profile data
const profile = {
	name: 'Andrew Long',
	bio: 'Full Stack Developer | SEO Expert ',
	avatar: '/images/drew.png',
};

// Social links with icons
const socialLinks = [
	{
		id: 1,
		label: 'Instagram',
		url: 'https://www.instagram.com/idrewdev/',
		icon: 'mdi:instagram',
		// icon: 'ph:globe-bold', // Professional globe icon
	},
	{
		id: 2,
		label: 'LinkedIn',
		url: 'https://www.linkedin.com/in/idrewlong/',
		icon: 'mdi:linkedin',
	},
	{
		id: 3,
		label: 'GitHub',
		url: 'https://github.com/idrewlong',
		icon: 'mdi:github',
	},
	{
		id: 4,
		label: 'Twitter',
		url: '#',
		icon: 'simple-icons:x', // New X/Twitter icon
	},
	{
		id: 5,
		label: 'Discord',
		url: '#',
		icon: 'ic:baseline-discord',
	},
	{
		id: 6,
		label: 'Contact',
		url: 'mailto:idrewlong@gmail.com',
		icon: 'heroicons:envelope-solid',
	},
];
</script>
