<template>
  <section class="flex flex-col rounded-sm py-4">
    <header class="grid place-items-center text-center mx-1">
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
</script>
