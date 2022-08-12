<template>
  <div v-if="athlete">
    <Header :athlete="athlete" />
    <ReportTable :athlete="athlete" />
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
import Header from "./Header.vue";
import ReportTable from "./ReportTable.vue";

defineProps({
  athlete: {
    type: Object,
    required: false,
  },
});
</script>
