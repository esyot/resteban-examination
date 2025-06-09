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
</script>

<template>
  <Section1 />
  <Section2 />
  <Section3 :founder="founder" />
  <Section4 />
  <Section5 :accordionItems="accordionItems" />
  <Section6 :testimonials="testimonials" />
  <Section7 :steps="steps" :dailySteps="dailySteps" />

  <Footer />
</template>
