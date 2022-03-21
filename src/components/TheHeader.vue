<template>
  <header class="flex gap-4 bg-green-200 py-4">
    <div class="flex gap-2 items-center ml-2">
      <img src="../assets/logo.png" alt="Vue Logo" class="w-16" />
      <span class="text-2xl font-semibold text-black">{{ props.title }}</span>
    </div>
  </header>
</template>

<script setup>
const props = defineProps({
  title: {
    type: String,
    default: 'Day 15'
  }
});
</script>
