<template>
  <v-app class="border-top">
    <v-main>
      <AcademicFitReport :athlete="athlete" />
    </v-main>
  </v-app>
</template>

<script setup lang="ts">
import AthleteData from "@/assets/data.json";
import AcademicFitReport from "./components/AcademicFitReport/AcademicFitReport.vue";

console.log({ AthleteData });

const athlete = AthleteData.data[0];
</script>

<style scoped>
.border-top {
  border-top: 9px solid #00b4ff;
}
</style>
