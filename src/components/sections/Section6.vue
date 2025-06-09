<script setup>
import { defineProps, ref, computed } from "vue";

const props = defineProps({
  testimonials: Array,
});

const current = ref(0);

function next() {
  current.value = (current.value + 1) % props.testimonials.length;
}
function prev() {
  current.value =
    (current.value - 1 + props.testimonials.length) % props.testimonials.length;
}

const isMobile = ref(false);

if (typeof window !== "undefined") {
  const checkMobile = () => {
    isMobile.value = window.innerWidth < 640;
  };
  checkMobile();
  window.addEventListener("resize", checkMobile);
}
</script>

<template>
  <section
    class="flex flex-col sm:flex-row justify-around space-x-0 items-start bg-stone-600 w-full mt-30 p-4 sm:px-30"
  >
    <div v-if="isMobile" class="w-full flex flex-col items-center">
      <div class="relative w-full">
        <div
          class="bg-orange-100 rounded-br-[80px] rounded-tl-[80px] p-6 mx-2 transition-all duration-300"
        >
          <div class="m-2">
            <h1 class="font-bold">"{{ testimonials[current].quote }}"</h1>
            <small class="text-gray-800/70">{{ testimonials[current].small }}</small>
            <div class="flex items-center gap-2 mt-6">
              <img
                :src="testimonials[current].img"
                alt=""
                class="w-10 h-10 sm:w-14 sm:h-14 rounded-full object-cover"
              />
              <span class="text-2xl sm:text-3xl tangerine-bold leading-none">{{
                testimonials[current].name
              }}</span>
            </div>
          </div>
        </div>
      </div>
      <div class="flex items-center w-full justify-between mt-4">
        <button @click="prev" class="text-orange-100">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M15 19l-7-7 7-7"
            />
          </svg>
        </button>

        <div class="flex justify-center gap-4">
          <span
            v-for="(t, i) in testimonials"
            :key="i"
            class="w-2 h-2 rounded-full"
            :class="i === current ? 'bg-orange-400' : 'bg-orange-200'"
          ></span>
        </div>

        <button @click="next" class="text-orange-100">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M9 5l7 7-7 7"
            />
          </svg>
        </button>
      </div>
    </div>

    <div v-else class="flex flex-row w-full justify-around space-x-6">
      <div class="flex flex-col justify-start self-start w-1/2">
        <div class="mb-6">
          <h1 class="text-white text-3xl font-bold font-serif">
            See how women have been impacted by the
          </h1>
          <span class="text-3xl text-orange-200 font-bold font-serif"
            >power of love:</span
          >
        </div>
        <div class="bg-orange-100 rounded-br-[150px] p-12">
          <div class="m-4">
            <h1 class="font-bold font-serif mb-4">"{{ testimonials[0].quote }}"</h1>
            <small class="text-gray-800/60">{{ testimonials[0].small }}</small>
            <div class="flex items-center gap-2 mt-4">
              <img
                :src="testimonials[0].img"
                alt=""
                class="w-10 h-10 sm:w-14 sm:h-14 rounded-full object-cover"
              />
              <span class="text-2xl sm:text-3xl tangerine-bold leading-none">{{
                testimonials[0].name
              }}</span>
            </div>
          </div>
        </div>
      </div>
      <div class="flex flex-col justify-start self-start w-1/2">
        <div class="bg-orange-100 rounded-tl-[150px] p-12">
          <div class="flex flex-col justify-center mx-4">
            <h1 class="font-bold font-serif mb-4">"{{ testimonials[1].quote }}"</h1>
            <small class="text-gray-800/75">{{ testimonials[1].small }}</small>
            <div class="flex items-center gap-2 mt-4">
              <img
                :src="testimonials[1].img"
                alt=""
                class="w-10 h-10 sm:w-14 sm:h-14 rounded-full object-cover"
              />
              <span class="text-2xl sm:text-3xl tangerine-bold leading-none">{{
                testimonials[1].name
              }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
