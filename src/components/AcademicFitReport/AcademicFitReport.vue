<template>
  <v-container v-if="athlete">
    <ReportHeader :athlete="athlete" />
    <ReportTable :athlete="athlete" />
    <ReportFooter />
  </v-container>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
import ReportTable from "./ReportTable.vue";
import ReportHeader from "./ReportHeader.vue";
import ReportFooter from "./ReportFooter.vue";

defineProps({
  athlete: {
    type: Object,
    required: false,
  },
});
</script>
