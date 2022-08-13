<template>
  <v-footer :absolute="true" height="35px" class="footer">
    <v-row class="items">
      <p>
        * Rankings for Division I schools based on NCAA data (www.ncaa.com) and
        rankings for Division II & III schools are based on data from Hero
        Sports (www.herosports.com/rankings)
      </p>
      <p>
        ** GPA is based on SportsRecruits members who have shown interest in
        (favorited) the school and have provided their GPA on their profile
      </p>
      <p>
        *** SAT and ACT scores based on national data provided by the National
        Center of Education Statistics- https://nces.ed.gov/ipeds/
      </p>
    </v-row>
  </v-footer>
</template>

<script setup lang="ts"></script>

<style scoped>
.footer {
  position: absolute;
  bottom: 0;
}
.items p {
  font-size: 14px;
  padding-bottom: 0.75rem;
}
</style>
