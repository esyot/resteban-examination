<script setup>
import { defineProps, ref } from "vue";

const props = defineProps({
  accordionItems: {
    type: Array,
    required: true,
  },
});

const openIndex = ref(null);

const toggleAccordion = (idx) => {
  openIndex.value = openIndex.value === idx ? null : idx;
};
</script>

<template>
  <section class="flex flex-col sm:flex-row justify-around mt-30 sm:mx-30">
    <div class="sm:order-1 order-2 w-full">
      <div v-for="(item, idx) in 3" :key="idx" class="mb-4 px-6">
        <div
          class="list-none border-b-2 pb-4 mb-4 mt-4 cursor-pointer"
          @click="toggleAccordion(idx)"
        >
          <div class="flex items-center justify-between w-full">
            <h1 class="text-2xl font-bold font-serif">
              {{ accordionItems[idx].title }}
            </h1>
            <span
              :class="[
                'inline-flex items-center justify-center rounded-full border border-orange-800 text-orange-800 transition-transform duration-300',
                openIndex === idx ? 'bg-orange-100 rotate-180' : 'rotate-0',
                'aspect-square w-10 min-w-[2.5rem] min-h-[2.5rem]',
              ]"
            >
              <svg
                v-if="openIndex === idx"
                xmlns="http://www.w3.org/2000/svg"
                class="w-6 h-6 text-orange-800 transition-transform duration-300"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="2"
              >
                <line x1="5" y1="12" x2="19" y2="12" />
              </svg>
              <svg
                v-else
                xmlns="http://www.w3.org/2000/svg"
                class="w-6 h-6 text-orange-800 transition-transform duration-300"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
                stroke-width="2"
              >
                <line x1="12" y1="5" x2="12" y2="19" />
                <line x1="5" y1="12" x2="19" y2="12" />
              </svg>
            </span>
          </div>
        </div>

        <div
          v-show="openIndex === idx"
          class="overflow-hidden mt-2 transition-all duration-300 ease-in-out"
          :class="openIndex === idx ? 'max-h-96 opacity-100' : 'max-h-0 opacity-0'"
        >
          <p>
            {{ accordionItems[idx].content }}
          </p>
        </div>
      </div>
    </div>
    <div class="sm:order-2 order-1 flex justify-center items-start mx-6">
      <img
        src="/assets/images/mask-group-120-DkyejoM-.webp"
        alt=""
        class="w-full h-auto"
      />
    </div>
  </section>
</template>
