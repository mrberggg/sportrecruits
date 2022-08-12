<template>
  <div v-if="athlete">
    <!-- <div v-for="el in athlete.report" :key="el.school">
      {{ el.school }}
      <SchoolGpa
        :school-gpa-average="el.gpa['50%']"
        :student-gpa="athlete.gpa"
      />
    </div> -->
  </div>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
import SchoolGpa from "./SchoolGpa.vue";

defineProps({
  athlete: {
    type: Object,
    required: false,
  },
});
</script>
