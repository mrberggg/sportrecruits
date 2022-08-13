<template>
  <v-table density="compact">
    <thead>
      <tr>
        <th rowspan="2">School Name</th>
        <th rowspan="2">Athletic Div</th>
        <th rowspan="2">Conference</th>
        <th>Ranking*</th>
        <th colspan="5">GPA**</th>
        <th>SAT Reading***</th>
        <th>SAT Math***</th>
        <th>ACT Composite***</th>
      </tr>
      <tr>
        <th>(DI NCAA)<br />(DII & DIII Hero Sports)</th>
        <th>Min</th>
        <th>25%</th>
        <th>50%</th>
        <th>75%</th>
        <th>Max</th>
        <th>25%-75%</th>
        <th>25%-75%</th>
        <th>25%-75%</th>
      </tr>
    </thead>
    <tbody>
      <ReportTableRow
        v-for="item in athlete.report"
        :item="item"
        :athlete="athlete"
        :key="item.ranking"
      ></ReportTableRow>
    </tbody>
  </v-table>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
import ReportTableRow from "./ReportTableRow.vue";

defineProps({
  athlete: {
    type: Object,
    required: true,
  },
});
</script>

<style scoped>
.v-table > .v-table__wrapper > table > tbody > tr > td,
.v-table > .v-table__wrapper > table > thead > tr > th {
  text-align: center;
  white-space: nowrap;
}
.v-locale--is-ltr .v-table > .v-table__wrapper > table > thead > tr > th {
  text-align: center;
}
.v-table {
  height: 100%;
  overflow: auto;
  width: 100%;
}
thead {
  background-color: black;
  color: white;
}
</style>
