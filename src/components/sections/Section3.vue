<script setup>
import { defineProps } from "vue";

const props = defineProps({
  founder: {
    type: Object,
    required: true,
    default: () => ({
      name: "",
      testimony: "",
    }),
  },
});
</script>

<template>
  <section class="flex sm:flex-row flex-col justify-around sm:space-x-16 mt-30 sm:mx-30">
    <div class="flex flex-col max-w-xl text-center flex-1 sm:items-start items-center">
      <img
        src="/assets/images/marni-image-cluster-0aljjjUR.webp"
        alt=""
        class="mx-6 w-full h-auto max-w-xs sm:max-w-xl"
      />
    </div>

    <div class="flex-1 flex flex-col mx-6">
      <div>
        <h1 class="text-6xl font-bold font-serif">Meet our founder,</h1>
        <h1 class="text-6xl font-bold font-serif text-orange-800/50">
          {{ founder.name }}
        </h1>

        <span class="block min-w-64 text-lg mt-4">
          {{ founder.testimony }}
        </span>
      </div>
      <button
        class="sm:block hidden sm:w-90 w-full px-4 py-2 bg-orange-800 text-white cursor-pointer hover:opacity-50 rounded-full mt-8 transition-colors duration-300"
      >
        Discover Marni's Proven Process
      </button>

      <button
        class="sm:hidden sm:w-90 w-full px-4 py-2 bg-orange-800 text-white cursor-pointer hover:opacity-50 rounded-full mt-8 transition-colors duration-300"
      >
        Learn More
      </button>
    </div>
  </section>
</template>
