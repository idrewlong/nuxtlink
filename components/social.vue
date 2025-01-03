<template>
	<NuxtLink :to="href" class="group block relative">
		<div
			class="absolute -inset-1 bg-gradient-to-r from-pink-600 to-purple-600 rounded-lg opacity-40 blur group-hover:opacity-75 transition duration-200"
		></div>
		<div
			class="relative flex items-center bg-gray-900 rounded-lg px-6 py-4 transition-all duration-200 group-hover:bg-gray-800"
		>
			<div class="flex-1 flex items-center space-x-4">
				<Icon
					:name="icon"
					class="w-6 h-6 text-gray-300 group-hover:text-white transition-colors"
				/>
				<span
					class="text-gray-300 group-hover:text-white font-medium transition-colors"
				>
					{{ label }}
				</span>
			</div>
			<Icon
				name="heroicons:arrow-right"
				class="w-5 h-5 text-gray-400 group-hover:text-white transform group-hover:translate-x-1 transition-all"
			/>
		</div>
	</NuxtLink>
</template>

<script setup>
defineProps({
	href: {
		type: String,
		required: true,
	},
	icon: {
		type: String,
		required: true,
	},
	label: {
		type: String,
		required: true,
	},
});
</script>
