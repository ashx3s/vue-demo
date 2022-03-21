<template>
  <section class="flex flex-col rounded-sm py-4">
    <header v-if="!headerTrigger" class="grid place-items-center text-center">
      <h2 class="text-red-500 text-3xl md:text-4xl font-medium">Add a Title</h2>
    </header>
    <header v-else class="grid place-items-center text-center mx-1">
      <h2 class="text-black text-3xl md:text-4xl font-medium">{{ props.title }}</h2>
    </header>

    <slot name="content"></slot>
  </section>
</template>

<script setup>
import BaseSectionHeader from './BaseSectionHeader';
const props = defineProps({
  title: {
    type: String
  }
});
const headerTrigger = false;
</script>
