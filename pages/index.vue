<template>
	<div class="relative w-screen h-screen flex justify-center items-center">
		<img
			class="w-full h-full object-cover"
			src="../assets/css/images/main-truck.jpg"
			alt="Main image with truck"
		/>
		<div
			class="mt-64 hover:border-b-2 hover:border-gray-700 sm:mt-48 absolute flex top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-6xl text-white transition-colors duration-1000"
		>
			<NuxtLink
				to="/"
				v-for="(span, index) in spans"
				:key="index"
				:class="{
					'color-transition': true,
					'grey-text': currentIndex === index,
				}"
				class="appearOnStart text-4xl sm:text-6xl 2xl:text-8xl 2xl:mt-36 opacity-0 transition-opacity duration-1000 ease-in-out"
				>{{ span }}
			</NuxtLink>
		</div>
	</div>

	<div
		class="md:flex-row sm:flex mt-72 sm:mt-48 mx-0 px-0 sm:mx-12 text-center sm:text-justify"
	>
		<div
			class="flex justify-center items-center flex-1 bg-gray-50 border-2 rounded-md m-4 sm:m-10 h-48 text-center text-"
		>
			<h1 class="text-8xl text-gray-600">Anton Company</h1>
		</div>
		<div class="flex-1 bg-gray-100 border-2 rounded-md m-10 h-48">
			<img src="" />
		</div>
	</div>
	<div
	class="md:flex-row sm:flex mt-72 sm:mt-48 mx-0 px-0 sm:mx-12 text-center sm:text-justify"
>
	<div
		class="flex justify-center items-center flex-1 bg-gray-50 border-2 rounded-md m-4 sm:m-10 h-48 text-center text-"
	>
		<h1 class="text-8xl text-gray-600">Anton Company</h1>
	</div>
	<div class="flex-1 bg-gray-100 border-2 rounded-md m-10 h-48">
		<img src="" />
	</div>
</div>
<div
class="md:flex-row sm:flex mt-72 sm:mt-48 mx-0 px-0 sm:mx-12 text-center sm:text-justify"
>
<div
	class="flex justify-center items-center flex-1 bg-gray-50 border-2 rounded-md m-4 sm:m-10 h-48 text-center text-"
>
	<h1 class="text-8xl text-gray-600">Anton Company</h1>
</div>
<div class="flex-1 bg-gray-100 border-2 rounded-md m-10 h-48">
	<img src="" />
</div>
</div>
</template>

<style>
/* Add the following styles to your custom CSS file to control the changing text color */
@media screen and (min-width: 760px) {
	.color-transition {
		display: inline-block;
		transition: color 0.2s; /* Adjust the duration as needed */
	}

	.color-transition:hover {
		color: #3f444b; /* Change the color to your desired value on hover */
	}
}
.grey-text {
	color: #9ea3ab;
}

@keyframes fadeIn {
	0% {
		opacity: 0;
	}
	100% {
		opacity: 1;
	}
}

.appearOnStart {
	animation: fadeIn 1s ease-in-out 1s forwards;
}
</style>

<script>
export default {
	data() {
		return {
			spans: ["A", "N", "T", "O", "N", "", "C", "O", "M", "P", "A", "N", "Y"],
			currentIndex: -1,
			main: 0,
		};
	},
	methods: {
		toggleGreyColor() {
			if (this.currentIndex < this.spans.length) {
				this.currentIndex++;
			} else {
				// All spans have been processed; reset currentIndex and wait for 5 seconds
				this.currentIndex = -1;
				setTimeout(() => {
					this.toggleGreyColor(); // Start the process again
				}, 3000); // Wait for 5 seconds before starting again
				return;
			}

			setTimeout(() => {
				this.toggleGreyColor(); // Continue processing the next span
			}, 200); // Wait for 0.5 seconds before toggling the next span
		},
	},

	mounted() {
		setTimeout(() => {
			this.toggleGreyColor(); // Start the process when the component is mounted
		}, 3000);
	},
};
</script>
