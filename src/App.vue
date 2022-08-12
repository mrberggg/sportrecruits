<template>
  <div class="container">
    <AcademicFitReport :athlete="athlete" />
  </div>
</template>

<script setup lang="ts">
import AcademicFitReport from "@/components/AcademicFitReport.vue";
import AthleteData from "@/assets/data.json";

const athlete = AthleteData.data[0];
</script>
