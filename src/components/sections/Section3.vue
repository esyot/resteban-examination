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
  <section class="flex sm:flex-row flex-col justify-around mt-30 space-x-12">
    <div
      class="flex flex-col mx-2 max-w-xl text-center flex-1 sm:items-start items-center"
    >
      <img
        src="/assets/images/marni-image-cluster-0aljjjUR.webp"
        alt=""
        class="w-full h-auto max-w-xs sm:max-w-xl"
      />
    </div>

    <div class="flex-1 flex flex-col mx-6">
      <div>
        <h1 class="text-6xl font-bold font-serif">Meet our founder,</h1>
        <h1 class="text-6xl font-bold font-serif text-orange-500">{{ founder.name }}</h1>

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
