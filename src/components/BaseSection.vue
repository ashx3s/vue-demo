<template>
  <section class="flex flex-col rounded-sm py-4">
    <BaseSectionHeader />
    <slot name="section-header"></slot>
    <slot name="section-body"></slot>
    <slot name="section-footer"></slot>
  </section>
</template>
<script setup>
import BaseSectionHeader from './BaseSectionHeader';
</script>
