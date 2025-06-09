<script setup>
import { ref, computed, defineProps } from "vue";

const props = defineProps({
  dailySteps: {
    type: Array,
    required: true,
  },
  steps: {
    type: Array,
    required: true,
  },
});

const selectedDay = ref(1);

const selectDay = (day) => {
  selectedDay.value = day;
};

const currentDay = computed(() => {
  const step = props.dailySteps.find((step) => step.day === selectedDay.value);
  return step || { title: "", description: "" };
});
</script>

<template>
  <section
    class="flex flex-col sm:items-start items-center sm:flex-row justify-around mt-30"
  >
    <div class="sm:w-full flex justify-center">
      <h1 class="text-4xl font-bold font-serif whitespace-nowrap">
        What's on the agenda
      </h1>
    </div>

    <div class="w-full px-6">
      <ul
        class="flex flex-col sm:flex-row justify-around items-center bg-stone-500 rounded-[40px] sm:rounded-full py-2 sm:px-2 px-4 font-serif text-xl"
      >
        <li
          v-for="step in dailySteps"
          :key="step.day"
          @click="selectDay(step.day)"
          :class="[
            'rounded-full cursor-pointer text-center py-2 w-full ',
            selectedDay === step.day ? 'bg-orange-100' : '',
          ]"
        >
          Day {{ step.day }}
        </li>
      </ul>

      <div class="flex flex-col justify-center sm:items-start items-center mt-6">
        <h1 class="text-2xl font-bold font-serif">{{ currentDay.title }}</h1>
        <p class="">
          {{ currentDay.description }}
        </p>
      </div>

      <div class="mt-16">
        <ol class="pl-6 relative">
          <li
            v-for="(step, idx) in steps"
            :key="step.number"
            class="relative pl-6 mb-10 ml-4"
          >
            <div
              v-if="idx !== steps.length - 1"
              class="absolute -left-0.5 top-8 w-1 h-[calc(100%+2rem)] bg-orange-200 z-0"
            ></div>

            <div
              class="absolute -left-4 flex items-center justify-center w-8 h-8 bg-orange-500 text-white rounded-full font-bold border-2 border-orange-400"
              style="z-index: 1"
            >
              {{ step.number }}
            </div>

            <h3 class="text-lg font-bold font-serif mb-1">{{ step.title }}</h3>
            <p class="text-base text-gray-600 mx-2">
              {{ step.content }}
            </p>
          </li>
        </ol>
      </div>
    </div>
  </section>
</template>
