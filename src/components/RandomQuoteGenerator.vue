<script setup>
import { onMounted, ref } from 'vue';
import quotes from './quotes.js'; // Importing the quotes array

const currentQuote = ref({ text: '', author: '' });

const getRandomQuote = () => {
  const randomIndex = Math.floor(Math.random() * quotes.length);
  currentQuote.value = quotes[randomIndex];
};

onMounted(getRandomQuote);
</script>

<template>
  <div
    class="bg-gradient-to-tl from-lime-400 to-cyan-500 min-h-screen flex items-center justify-center"
  >
    <div class="bg-black max-w-xl mx-auto p-6 text-center border rounded-lg shadow-lg">
      <h1 class="text-2xl mb-5 text-white">Random Quote Generator</h1>
      <blockquote class="bg-gray-100 p-5 rounded-lg border border-gray-300 mb-5">
        <p class="text-lg mb-2">{{ currentQuote.text }}</p>
        <cite class="font-normal text-gray-500">{{ currentQuote.author }}</cite>
      </blockquote>

      <button
        @click="getRandomQuote"
        class="px-4 py-2 text-lg bg-lime-500 text-black rounded hover:bg-lime-700 hover:text-white"
      >
        New Quote
      </button>
    </div>
  </div>
</template>
