<template>
  <v-card>
    <v-card-title><h1>Contact Us</h1></v-card-title>
    <v-card-text>
      <v-text-field label="Name" required />
      <v-text-field label="Email" required />
    </v-card-text>
    <v-card-actions>
      <v-spacer />
      <v-btn color="blue darken-1" @click="close" text>Close</v-btn>
      <v-btn color="blue darken-1" @click="submit" text>Submit</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  methods: {
    close(e) {
      this.$emit("close", e);
    },
    submit(e) {
      this.$emit("submit", e);
    }
  }
};
</script>

<style lang="scss" scoped></style>
