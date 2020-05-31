<template>
  <v-app>
    <v-navigation-drawer
      v-if="hasDrawer"
      v-model="drawer"
      class="drawer"
      app
      dark
    >
      <side />
    </v-navigation-drawer>
    <v-app-bar color="transparent" elevation="0" app>
      <v-app-bar-nav-icon
        @click.stop="drawer = !drawer"
        v-if="hasDrawer"
      ></v-app-bar-nav-icon>
    </v-app-bar>
    <router-view />
  </v-app>
</template>

<script>
import Side from "@/views/Side";
export default {
  name: "App",
  components: { Side },
  data() {
    return {
      drawer: false
    };
  },
  computed: {
    hasDrawer() {
      return this.$vuetify.breakpoint.xsAndDown;
    }
  }
};
</script>

<style lang="scss">
* {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
}
.drawer {
  padding-top: 0px;
}

@media screen and (min-width: 960px) {
}
</style>
