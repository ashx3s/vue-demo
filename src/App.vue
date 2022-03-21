<template>
  <TheHeader />
  <header class="flex flex-col items-center justify-center h-40 py-4">
    <h1 class="text-5xl uppercase md:text-6xl lg:text-7xl">Main Page</h1>
  </header>
  <main class="grid grid-cols-1 md:grid-cols-2 md:gap-4">
    <section class="flex flex-col bg-gray-200 rounded-sm py-4">
      <header class="grid place-items-center">
        <h2 class="text-black text-2xl md:text-4xl font-semi-bold">Render a List</h2>
      </header>
      <div class="flex justify-center">
        <ul class="my-4">
          <li v-for="number in numberArray" :key="number.id" class="text-2xl">{{ number }}</li>
        </ul>
      </div>
    </section>
    <section class="flex flex-col bg-pink-200 rounded-sm py-4">
      <header class="grid place-items-center">
        <h2 class="text-black text-2xl md:text-4xl font-semi-bold">Render a Computed List</h2>
      </header>
      <div class="flex justify-center">
        <ul class="my-4">
          <li v-for="number in multipliedArray" :key="number.id" class="text-2xl">{{ number }}</li>
        </ul>
      </div>
    </section>
  </main>
</template>

<script setup>
import { computed } from 'vue';
import TheHeader from './components/TheHeader.vue';
const numberArray = [1, 2, 3, 4, 5];
const multipliedArray = computed(() => {
  return numberArray.map((num) => num * 5);
});
</script>
