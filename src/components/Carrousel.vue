<template>
  <div class="relative w-full overflow-hidden" role="region" aria-label="Image Carousel">
    <!-- Wrapper com largura dinâmica -->
    <div
      class="flex transition-transform duration-700 ease-in-out"
      :style="{ transform: `translateX(-${currentIndex * 100}%)` }"
    >
      <div
        v-for="(image, index) in carrouselImages"
        :key="index"
        class="w-full flex-shrink-0 h-56 md:h-96 relative"
      >
        <img
          :src="image"
          :alt="`Slide ${index + 1}`"
          class="w-full h-full object-cover"
          loading="lazy"
        />
      </div>
    </div>

    <!-- Indicators -->
    <div class="absolute z-30 flex -translate-x-1/2 space-x-3 bottom-5 left-1/2">
      <button
        v-for="(image, index) in carrouselImages"
        :key="index"
        @click="goToSlide(index)"
        class="w-3 h-3 rounded-full"
        :class="currentIndex === index ? 'bg-white' : 'bg-gray-400/50'"
        :aria-label="`Go to slide ${index + 1}`"
        :aria-current="currentIndex === index"
      ></button>
    </div>

    <!-- Controls -->
    <button
      type="button"
      @click="prevSlide"
      class="absolute top-0 left-0 z-30 flex items-center justify-center h-full px-4 cursor-pointer group focus:outline-none"
    >
      <span class="inline-flex items-center justify-center w-10 h-10 rounded-full bg-white/30 hover:bg-white/50">
        <svg class="w-4 h-4 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 6 10">
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 1 1 5l4 4"/>
        </svg>
        <span class="sr-only">Previous</span>
      </span>
    </button>

    <button
      type="button"
      @click="nextSlide"
      class="absolute top-0 right-0 z-30 flex items-center justify-center h-full px-4 cursor-pointer group focus:outline-none"
    >
      <span class="inline-flex items-center justify-center w-10 h-10 rounded-full bg-white/30 hover:bg-white/50">
        <svg class="w-4 h-4 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 6 10">
          <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 9 4-4-4-4"/>
        </svg>
        <span class="sr-only">Next</span>
      </span>
    </button>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

import image2 from "@/assets/imgs/image2.jpg";
import image3 from "@/assets/imgs/image3.jpg";

const carrouselImages = [image3, image2 ];
const currentIndex = ref(0);
const interval = ref(null);
const autoplay = true;
const delay = 5000;

function nextSlide() {
  currentIndex.value = (currentIndex.value + 1) % carrouselImages.length;
}

function prevSlide() {
  currentIndex.value =
    (currentIndex.value - 1 + carrouselImages.length) % carrouselImages.length;
}

function goToSlide(index) {
  currentIndex.value = index;
}

onMounted(() => {
  if (autoplay) {
    interval.value = setInterval(nextSlide, delay);
  }
});

onBeforeUnmount(() => {
  if (interval.value) clearInterval(interval.value);
});
</script>
