<script setup>
import { ref, computed } from "vue";
const steps = [
  {
    number: 1,
    title: "Understand Why",
    content:
      "Even though you've read all the self-help books and followed all the rules -- you're still single. Learn how to make our secret technology work for you so that you attract the hot, high-quality man your heart desires.",
  },
  {
    number: 2,
    title: "Learn 4 Characteristics that Attract Men",
    content:
      "Not just any men, but men who are open, vulnerable, and committed—so that no man will ever disappear on you again.",
  },
  {
    number: 3,
    title: "Reprogram Your Dating GPS",
    content:
      "Understand why no matter HOW you meet a man, it won't work until you reprogram your dating GPS to become 'the destination' for the men you want.",
  },
  {
    number: 4,
    title: 'Learn what "feminine" means now',
    content:
      "Especially as a successful woman—so you don’t have to jump into the girly-girl bucket to attract a high-quality man.",
  },
  {
    number: 5,
    title: "Remove Limiting Beliefs",
    content:
      'Eliminate the "Nothing works for me" belief so the universe knows you\'re lovable and sends you the right man to love.',
  },
];

const dailySteps = [
  {
    day: 1,
    title: "Clarify Your Intentions",
    description:
      "Take time today to deeply reflect on what you truly desire in a romantic relationship. Go beyond surface-level wants and consider the qualities, values, and emotional connection that are most important to you. Write down your thoughts in a journal, and be honest with yourself about your hopes, fears, and expectations. Setting clear intentions will help you navigate your dating journey with purpose and confidence, ensuring that you attract partners who align with your authentic self and long-term goals.",
  },
  {
    day: 2,
    title: "Identify Limiting Beliefs",
    description:
      "Spend today uncovering any negative beliefs or assumptions you hold about love, relationships, or your own worthiness. These could be thoughts like 'I'm not attractive enough,' 'All the good ones are taken,' or 'I'm destined to be alone.' Write each belief down and examine where it might have originated—perhaps from past experiences or societal messages. Challenge the validity of these beliefs by seeking evidence to the contrary and considering how they may be holding you back. Reframe each limiting belief into a positive, empowering statement that supports your growth and happiness.",
  },
  {
    day: 3,
    title: "Practice Self-Compassion",
    description:
      "Dedicate today to nurturing your self-worth and treating yourself with kindness. Choose an activity that makes you feel valued and cared for, such as writing a heartfelt letter to yourself, listing your strengths and achievements, or engaging in a favorite hobby. Reflect on your journey so far and acknowledge the progress you've made, no matter how small. Remember that self-compassion is not about ignoring your flaws, but about accepting yourself fully and recognizing that you are deserving of love and respect. Building a compassionate relationship with yourself lays the foundation for attracting and sustaining healthy, fulfilling relationships with others.",
  },
];

const selectedDay = ref(1);

const selectDay = (day) => {
  selectedDay.value = day;
};

const currentDay = computed(() => {
  const step = dailySteps.find((step) => step.day === selectedDay.value);
  return step || { title: "", description: "" };
});
</script>

<template>
  <section
    class="flex flex-col sm:items-start items-center sm:flex-row justify-around mt-16"
  >
    <div class="sm:w-full w-1/2 flex justify-center">
      <h1 class="text-3xl font-bold font-serif">What's on the agenda</h1>
    </div>

    <div class="w-full">
      <ul
        class="flex flex-col sm:flex-row px-4 justify-around items-center bg-stone-500 rounded-[40px] m-4 sm:rounded-full py-4 font-serif text-xl"
      >
        <li
          v-for="step in dailySteps"
          :key="step.day"
          @click="selectDay(step.day)"
          :class="[
            'rounded-full cursor-pointer text-center sm:text-left sm:w-auto w-full mx-6 px-4 py-2',
            selectedDay === step.day ? 'bg-orange-100 ' : '',
          ]"
        >
          Day {{ step.day }}
        </li>
      </ul>

      <div class="flex flex-col justify-center sm:items-start items-center mt-6">
        <h1 class="text-2xl font-bold font-serif">{{ currentDay.title }}</h1>
        <p class="mx-4">
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
