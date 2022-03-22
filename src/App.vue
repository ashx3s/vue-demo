<template>
  <TheHeader />
  <!-- Page Header -->
  <header class="flex flex-col items-center justify-center h-40 py-4">
    <h1 class="text-5xl uppercase md:text-6xl lg:text-7xl">Main Page</h1>
  </header>

  <BaseSection :title="sectionTitle">
    <template #content>
      <p class="max-w-prose text-xl mx-auto">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Alias amet saepe porro deserunt
        doloribus, veritatis enim rem suscipit ipsa! Dolore est vero, iusto provident harum vel eos
        itaque veniam iste quas corrupti doloribus molestiae incidunt quia dolores veritatis alias
        quod molestias necessitatibus optio porro, cumque aspernatur expedita. Ea, quasi maxime!
      </p>
    </template>
  </BaseSection>

  <!-- Page Content -->
  <main class="grid grid-cols-1 md:grid-cols-2 gap-4 mx-4">
    <!-- Section 1 -->
    <section class="flex flex-col bg-gray-200 rounded-sm py-4">
      <header class="grid place-items-center text-center mx-1">
        <h2 class="text-black text-3xl md:text-4xl font-medium">Render a List</h2>
      </header>
      <div class="flex justify-center">
        <ul class="my-4">
          <li v-for="number in numberArray" :key="number.id" class="text-2xl">{{ number }}</li>
        </ul>
      </div>
    </section>
    <!-- Section 2 -->
    <section class="flex flex-col bg-pink-200 rounded-sm py-4">
      <header class="grid place-items-center text-center mx-1">
        <h2 class="text-black text-3xl md:text-4xl font-medium">Render a Computed List</h2>
      </header>
      <div class="flex justify-center">
        <ul class="my-4">
          <li v-for="number in multipliedArray" :key="number.id" class="text-2xl">{{ number }}</li>
        </ul>
      </div>
    </section>
    <BaseSection :title="'Grocery Array'">
      <template #content>
        <ul class="text-xl text-center">
          <li v-for="product in groceries" :key="product.id">
            {{ product.item }} -- {{ product.cost }}
          </li>
        </ul>
      </template>
    </BaseSection>
    <BaseSection :title="'Groceries with Tax'">
      <template #content>
        <ul class="text-xl text-center">
          <li v-for="product in groceriesWithTax" :key="product.id">
            {{ product.name }} -- {{ product.cost }}
          </li>
        </ul>
      </template>
    </BaseSection>
    <section></section>
  </main>
</template>

<script setup>
// Imports
import { computed } from 'vue';
import TheHeader from './components/ui/TheHeader.vue';
import BaseSection from './components/layout/BaseSection.vue';
import BaseSectionHeader from './components/BaseSectionHeader';

// Lifecycle Hook: onMounted
import { onMounted } from 'vue';
onMounted(() => {
  console.log(`This is the component being mounted`);
});

// Variables
const sectionTitle = 'Demo Section';

const numberArray = [1, 2, 3, 4, 5];

const multipliedArray = computed(() => {
  return numberArray.map((num) => num * 5);
});

// Groceries
const groceries = [
  {
    item: 'bread',
    cost: 5.45
  },
  {
    item: 'eggs',
    cost: 4.5
  },
  {
    item: 'tuna',
    cost: 2.25
  },
  {
    item: 'avocado',
    cost: 3.0
  }
];

// Computed Tax Groceries
const groceriesWithTax = computed(() => {
  return groceries.map((product) => ({
    name: product.item,
    cost: parseFloat((product.cost * 1.05).toFixed(2))
  }));
});

// calculate sum total of items in the cart
const getCartTotal = (arr) => {
  arr.reduce((acc, curr) => acc + curr.cost, 0);
};
</script>
