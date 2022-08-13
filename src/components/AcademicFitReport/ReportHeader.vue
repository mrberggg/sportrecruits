<template>
  <v-row v-if="athlete" class="report-header">
    <div class="avatar">
      <report-header-avatar :athlete="athlete"></report-header-avatar>
    </div>
    <v-col class="details">
      <h1>{{ athlete.name }}</h1>
      <v-row class="detail-columns">
        <v-col>
          <p>
            <label>Sport:</label>
            {{ athlete.sport }}
          </p>
          <p>
            <label>Class:</label>
            {{ athlete.grad_year }}
          </p>
          <p>
            <label>Club:</label>
            {{ athlete.club.name }}
          </p>
        </v-col>
        <v-col>
          <div>
            <label>High School:</label>
            {{ athlete.high_school.name }}
          </div>
          <p>
            <label>GPA:</label>
            {{ athlete.gpa }}
          </p>
          <p>
            <label>Desired Major</label>
            {{ athlete.major }}
          </p>
        </v-col>
      </v-row>
    </v-col>
    <v-spacer></v-spacer>
    <v-col class="header">
      <v-img src="/sr-insights.png" max-height="55px" />
      <div class="sub-header">Academic Fit Report</div>
    </v-col>
  </v-row>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
import ReportHeaderAvatar from "./ReportHeaderAvatar.vue";

defineProps({
  athlete: {
    type: Object,
    required: false,
  },
});
</script>

<style scoped>
.report-header {
  font-size: 14px;
  margin: 40px 0;
}
.details {
  margin-top: -15px;
}
.details h1 {
  color: #00b4ff;
  font-size: 19px;
}
label {
  font-weight: 700;
}
.v-avatar.v-avatar--size-default {
  --v-avatar-height: 100px;
}
.sub-header {
  text-align: right;
  padding-right: 43px;
}
@media (max-width: 768px) {
  .report-header {
    display: block;
    margin-bottom: 30px;
  }
  .avatar,
  .details,
  .header {
    margin-bottom: 20px;
    text-align: center;
    width: 100%;
  }
  .detail-columns {
    padding: 0 25px;
    text-align: left;
  }
  .sub-header {
    text-align: center;
    padding-right: 0;
    margin-top: 10px;
  }
}
</style>
