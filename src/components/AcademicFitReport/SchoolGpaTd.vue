<template>
  <td :style="{ backgroundColor: backgroundColor }">
    {{ schoolGpaAverage }}
  </td>
</template>

<script setup lang="ts">
import { computed, defineProps } from "vue";

const props = defineProps({
  schoolGpaAverage: {
    type: Number,
    required: true,
  },
  studentGpa: {
    type: Number,
    required: true,
  },
});

const backgroundColor = computed(() => {
  const { schoolGpaAverage, studentGpa } = props;
  // - school gpa above the player's gpa by more than 0.10 color is #d7737d
  if (schoolGpaAverage - 0.1 > studentGpa) return "#d7737d";
  // - school gpa above the player's gpa by up to 0.10 color is #c194b5
  if (schoolGpaAverage > studentGpa) return "#c194b5";
  // - school gpa equal to the player's gpa color is #b4a7d6
  if (schoolGpaAverage === studentGpa) return "#b4a7d6";
  // - school gpa under the player's  gpa by less than 0.10 color is #a6a8da
  if (schoolGpaAverage > studentGpa - 0.1) return "#a6a8da";
  // - school gpa under the player's gpa by more than 0.10 color is #75ace5
  return "#75ace5";
});
</script>
