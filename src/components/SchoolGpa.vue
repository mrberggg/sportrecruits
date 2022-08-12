<template>
  <div>{{ schoolGpaAverage }}</div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

defineProps({
  schoolGpaAverage: {
    type: Number,
    required: true,
  },
  studentGpa: {
    type: Number,
    required: true,
  },
});
</script>
