<template>
  <tr>
    <td>{{ item.school }}</td>
    <td>{{ item.division }}</td>
    <td>{{ item.conference }}</td>
    <td class="center">{{ item.ranking }}</td>
    <td>{{ item.gpa.min }}</td>
    <td>{{ item.gpa["25%"] }}</td>
    <SchoolGpaTd
      :school-gpa-average="item.gpa['50%']"
      :student-gpa="athlete.gpa"
    />
    <td>{{ item.gpa["75%"] }}</td>
    <td>{{ item.gpa.max }}</td>
    <td class="center">{{ getRangeDisplay(item.sat.reading) }}</td>
    <td class="center">{{ getRangeDisplay(item.sat.math) }}</td>
    <td class="center">{{ getRangeDisplay(item.act) }}</td>
  </tr>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
import SchoolGpaTd from "./SchoolGpaTd.vue";

const getRangeDisplay = ({
  min,
  max,
}: {
  min: number | string;
  max: number | string;
}) => {
  if (!min || !max || min === "N/A" || max === "N/A") {
    return "Not Reported";
  }

  return `${min}-${max}`;
};

defineProps({
  athlete: {
    type: Object,
    required: true,
  },
  item: {
    type: Object,
    required: true,
  },
});
</script>

<style scoped>
.center {
  text-align: center;
}
tbody tr {
  white-space: nowrap;
}
tbody tr:nth-child(2n) {
  background-color: #dbe3f0;
}
.v-table table tr:nth-child(2n):hover {
  background-color: #cdd8ea;
}
</style>
