<template>
  <v-container class="content-container d-flex pa-0">
    <v-row justify="center" align="center" fill-height>
      <v-col lg="10" offset-lg="2">
        <v-container tag="section" class="content pa-0 ma-0">
          <v-row>
            <v-col offset="2" offset-md="3" offset-sm="2" cols="3">
              <v-img src="@/assets/hello.svg" :aspect-ratio="170 / 110" />
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <h1 class="text-center">
                You have an <span>idea</span>.<br />
                We will translate it <br class="d-sm-none" />into reality.
              </h1>
              <h2 class="text-center subtitle">
                Our approach to marketing is unique.<br class="d-sm-none" />We
                have been enabling businesses to<br />
                effectively engage their customers.
              </h2>
            </v-col>
          </v-row>
          <v-row justify="center">
            <v-col class="text-center">
              <v-dialog v-model="dialog" persistent max-width="300px">
                <template v-slot:activator="{ on }">
                  <v-btn
                    outlined
                    v-on="on"
                    class="white--text"
                    :size="buttonSize"
                    >Let's get started with 10% discount</v-btn
                  >
                </template>
                <contact-form @close="dialog = false" />
              </v-dialog>
            </v-col>
          </v-row>
          <v-row justify="center">
            <v-col cols="2" lg="1">
              <v-img src="@/assets/bubble.svg" />
            </v-col>
          </v-row>
          <v-row justify="center">
            <v-col cols="9" sm="4">
              <p
                class="text-center pink lighten-4 font-weight-medium white--text promotion"
              >
                Effective marketing communication
              </p>
              <p
                class="text-center pink lighten-4 font-weight-medium white--text promotion"
              >
                boost your business by 500%
              </p>
            </v-col>
          </v-row>
        </v-container>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import ContactForm from "./Form";

export default {
  components: { ContactForm },
  data() {
    return {
      dialog: false
    };
  },
  computed: {
    buttonSize() {
      const size = {
        xs: "x-small",
        sm: "x-large",
        lg: "x-large",
        xl: "x-large"
      }[this.$vuetify.breakpoint.name];
      return size ? { [size]: true } : {};
    }
  }
};
</script>

<style lang="scss" scoped>
.content-container {
  height: 100%;
}
h1 {
  font-size: 3em;
  line-height: 1.1;
  text-transform: uppercase;
  color: white;
  span {
    color: black;
  }
}
h2.subtitle {
  font-size: 1.2em;
}
p.promotion {
  font-size: 1.2em;
  margin-bottom: 1px !important;
}

@media screen and (max-width: 600px) {
  h1 {
    font-size: 1.2em;
  }
  h2.subtitle {
    font-size: 1em;
  }
  p.promotion {
    font-size: 1em;
  }
}
</style>
