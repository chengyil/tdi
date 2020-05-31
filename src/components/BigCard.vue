<template>
  <v-sheet tile>
    <v-img
      :src="src"
      :srcset="srcset"
      :height="height"
      :aspect-ratio="aspectRatio"
      :position="position"
    >
      <slot />
    </v-img>
  </v-sheet>
</template>

<script>
export default {
  name: "BigCard",
  props: {
    position: {
      type: String,
      default: "center center"
    },
    aspectRatio: {
      type: Number,
      default: 1.7
    },
    src: {
      type: String,
      default: undefined,
      required: true
    },
    height: {
      type: [Number, String],
      default: "100vh"
    },
    srcset: {
      type: String,
      default: undefined
    }
  }
};
</script>

<style lang="scss" scoped>
.big-card-container {
  padding: 96px 0;
}
</style>
