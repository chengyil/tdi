<template>
  <v-row class="pa-0 ma-0">
    <v-col class="content">
      <home-content />
    </v-col>
  </v-row>
</template>

<script>
import HomeContent from "./Content";
export default {
  name: "Home",
  components: { HomeContent }
};
</script>
<style lang="scss" scoped>
.content {
  padding-top: 0px;
  background-image: url("../../assets/bg.png");
  background-repeat: repeat-x;
  height: 100vh;
}
</style>
