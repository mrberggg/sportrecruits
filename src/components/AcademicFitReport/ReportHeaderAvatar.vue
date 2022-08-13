<template>
  <v-avatar v-if="athlete.profile_image">
    <v-img :src="athlete.profile_image" />
  </v-avatar>
  <v-avatar v-else :style="{ backgroundColor }" class="initial">
    {{ firstLetterOfLastName }}
  </v-avatar>
</template>

<script setup lang="ts">
import { computed, defineProps } from "vue";

const props = defineProps({
  athlete: {
    type: Object,
    required: true,
  },
});

const firstLetterOfLastName = computed(() => {
  const firstLetterOfLastNameRegex = /\s(\S)\S*$/;

  return props.athlete.name.match(firstLetterOfLastNameRegex)[1];
});

const backgroundColor = computed(() => {
  const { value } = firstLetterOfLastName;
  if (!value) return "";
  if (value.match(/[a-e]/) !== null) return "#f1603c";
  if (value.match(/[f-j]/) !== null) return "#f1603c";
  if (value.match(/[k-n]/) !== null) return "#f1603c";
  if (value.match(/[o-r]/) !== null) return "#f1603c";
  if (value.match(/[s-v]/) !== null) return "#f1603c";
  return "#ffa94d";
});
</script>

<style scoped>
.initial {
  font-size: 3.5rem;
  font-weight: 700;
}
</style>
