<template>
  <v-app>
    <v-navigation-drawer app class="drawer">
      <side />
    </v-navigation-drawer>

    <v-content class="ma-0 pa-0">
      <v-container fluid class="pa-0">
        <router-view class="pa-0" />
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import Side from "@/views/Side";
export default {
  name: "App",
  components: { Side }
};
</script>

<style lang="scss">
* {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
.drawer {
  background-color: transparent !important;
  border-color: white !important;
  border: none !important;
  border-right: 1px solid white !important;
  padding-top: 0px;
}
</style>
