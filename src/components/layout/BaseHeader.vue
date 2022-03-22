<template>
  <header class="grid place-items-center text-center mx-1">
    <h2 class="text-black text-3xl md:text-4xl font-medium">{{ props.title }}</h2>
  </header>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String
  }
});
</script>
