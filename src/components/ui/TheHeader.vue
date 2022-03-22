<template>
  <header class="flex gap-4 bg-green-200 py-4">
    <TheLogo />
    <TheNavBar />
    <TheToggle />
  </header>
</template>

<script setup>
import TheLogo from '../TheLogo.vue';
import TheNavBar from '../TheNavBar.vue';
import TheToggle from '../TheToggle.vue';
const title = 'Props Day';
</script>
