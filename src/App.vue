<template>
  <v-app class="page-container">
    <v-main>
      <AcademicFitReport :athlete="athlete" />
    </v-main>
  </v-app>
</template>

<script setup lang="ts">
import AthleteData from "@/assets/data.json";
import AcademicFitReport from "./components/AcademicFitReport/AcademicFitReport.vue";

const athlete = AthleteData.data[0];
</script>

<style scoped>
.page-container {
  border-bottom: 9px solid #00b4ff;
  border-top: 9px solid #00b4ff;
}
</style>
