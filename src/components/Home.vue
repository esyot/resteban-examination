<script setup>
import { ref } from "vue";

import Section1 from "./sections/Section1.vue";
import Section2 from "./sections/Section2.vue";
import Section3 from "./sections/Section3.vue";
import Section4 from "./sections/Section4.vue";
import Section5 from "./sections/Section5.vue";
import Section6 from "./sections/Section6.vue";
import Section7 from "./sections/Section7.vue";
import Footer from "./Footer.vue";

const accordionItems = [
  {
    title: "Let go of limiting beliefs",
    content: `If you don't think you deserve a good man, you're grappling with accepting
that a relationship is not in the cards for you, or you think you have to
settle for a less than ideal soul mate, we'll help you identify and learn to
let go of what's holding you back.`,
  },
  {
    title: "Break down barriers",
    content: `Many women unknowingly build emotional walls as a way to protect themselves
from past hurt or disappointment. Breaking down these barriers means
recognizing the patterns that keep you guarded and learning how to open up
to genuine connection. We'll guide you to identify these self-imposed limits
and empower you to embrace vulnerability, so you can experience deeper, more
meaningful relationships.`,
  },
  {
    title: "Fall in love with your true self",
    content: `Falling in love with your true self means embracing every part of who you
are—your strengths, your quirks, and even your imperfections. It's about
letting go of self-judgment and learning to appreciate your unique
qualities. When you accept and honor your authentic self, you naturally
attract relationships that are genuine and fulfilling. We'll help you
cultivate self-compassion and confidence, so you can show up fully in your
life and relationships, knowing you are worthy of love just as you are.`,
  },
];

const founder = {
  name: "Marni",
  testimony:
    "Having been married for 17 years, divorced, and successfully dated again in today's complex social environment, and now happily married, Marni understands what it feels like to be lonely and sick of wasting time going on dates and having relationships with unavailable men that go nowhere. Through her own journey to find love, Marni discovered that creating a process to shorten the journey for other women suffering from the inability to create emotionally safe and fulfilling life relationships was truly the mission of her soul and purpose.",
};

const testimonials = [
  {
    quote:
      "Once Marni held me accountable, it was easier for me to finally recognizes when Mr.Right (Mark) came along.",
    small:
      "If I had followed the guiding hand of Marni, I wouldn't have been ready to accept the moments and opportunities presented to me everyday.",
    img: "/assets/images/janice.webp",
    name: "Janice",
  },
  {
    quote:
      "I am now much more grounded and confident and I feel like I'm living the lide that i wanted to live now.",
    small:
      "When I first joined the program, the best initial results I got were me actually loving who i am. I think I always had an appreciation for myself, but I didn't truly beleive that I was worthy of great things.",
    img: "/assets/images/fill.webp",
    name: "Fill",
  },
];
</script>

<template>
  <Section1 />
  <Section2 />
  <Section3 :founder="founder" />
  <Section4 />
  <Section5 :accordionItems="accordionItems" />
  <Section6 :testimonials="testimonials" />
  <Section7 />

  <Footer />
</template>
