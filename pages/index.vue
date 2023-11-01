<template>
	<!-- <div class="w-screen h-screen flex justify-center items-center">
    <img class="w-full h-full object-cover" src="" alt="Our company's truck.">
  </div> -->

	<!-- ---------------------------------------------------------------------- -->
	<!-- <div class="relative w-screen h-screen flex justify-center items-center">
  <img class="w-full h-full object-cover" src="your-image.jpg" alt="Your Image Description">
  <h1 class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-6xl">
    <span class="color-transition">Y</span>
    <span class="color-transition">o</span>
    <span class="color-transition">u</span>
    <span class="color-transition">r</span>
    <span class="color-transition">T</span>
    <span class="color-transition">e</span>
    <span class="color-transition">x</span>
    <span class="color-transition">t</span>
  </h1>
</div> -->

	<!-- ---------------------------------------------------------------------- -->
	<div class="relative w-screen h-screen flex justify-center items-center">
		<img
			class="w-full h-full object-cover"
			src="../assets/css/images/main-truck.jpg"
			alt="Your Image Description"
		/>
		<div
			id="changing-text"
			class="mt-64 sm:mt-48 absolute flex top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 text-6xl text-white transition-colors duration-1000"
		>
			<NuxtLink to="/"
				v-for="(span, index) in spans"
				:key="index"
				:class="{
					'color-transition': true,
					'grey-text': currentIndex === index,
          'opacity': main
				}"
        class="text-4xl"
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
	color: #afb4bd;
}
</style>

<script>
// const spans = document.querySelectorAll(".color-transition");
// let currentIndex = 0;

// function toggleGreyColor() {
// 	spans[currentIndex].style.color = "grey"; // Set the color to grey
// 	setTimeout(() => {
// 		spans[currentIndex].style.color = ""; // Reset the color to default
// 		currentIndex = (currentIndex + 1) % spans.length; // Move to the next span
// 		toggleGreyColor(); // Repeat the process for the next span
// 	}, 5000); // Wait for 5 seconds before toggling the next span
// }

// toggleGreyColor(); // Start the process
export default {
	data() {
		return {
			spans: ["A", "N", "T", "O", "N", "", "C", "O", "M", "P", "A", "N", "Y"],
			currentIndex: 0,
      main: 0
		};
	},
	methods: {
		// toggleGreyColor() {
		// 	this.currentIndex = (this.currentIndex + 1) % this.spans.length;
		// 	setTimeout(() => {
		// 		this.toggleGreyColor();
		// 	}, 300); // Wait for 5 seconds before toggling the next span
		// },

		toggleGreyColor() {
			if (this.currentIndex < this.spans.length) {
				this.currentIndex++;
			} else {
				// All spans have been processed; reset currentIndex and wait for 5 seconds
				this.currentIndex = -1;
				setTimeout(() => {
					this.toggleGreyColor(); // Start the process again
				}, 5000); // Wait for 5 seconds before starting again
				return;
			}

			setTimeout(() => {
				this.toggleGreyColor(); // Continue processing the next span
			}, 150); // Wait for 0.5 seconds before toggling the next span
		},
    toggleAppearingHeading() {
      
    }

  },

		mounted() {
			this.toggleGreyColor(); // Start the process when the component is mounted
      this.toggleAppearingHeading()
		},
};
</script>
