<template>
  <v-container v-if="athlete">
    <ReportHeader :athlete="athlete" />
    <ReportTable :athlete="athlete" />
  </v-container>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
import ReportTable from "./ReportTable.vue";
import ReportHeader from "./ReportHeader.vue";

defineProps({
  athlete: {
    type: Object,
    required: false,
  },
});
</script>
