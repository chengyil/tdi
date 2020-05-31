<template>
  <div>
    <big-card
      max-height="100vh"
      height="100%"
      :position="position"
      :src="require('@/assets/bg-768.png')"
      :srcset="srcset"
    >
      <v-container class="home-content">
        <v-row
          v-if="!smAndDown"
          style="height: 100vh"
          justify="space-around"
          align-content="space-around"
        >
          <v-col cols="3"> <side light/></v-col>
          <v-col cols="9">
            <v-container>
              <v-row>
                <v-col cols="12">
                  <v-img
                    src="@/assets/hello.svg"
                    max-height="68px"
                    contain
                    position="15% 20%"
                  />
                  <h1 class="text-center">You have an <span>idea</span>.</h1>
                  <h1 class="text-center">
                    We will translate it into reality.
                  </h1>
                </v-col>
                <v-col cols="12">
                  <br />
                  <h2 class="subtitle text-center">
                    Our approach to marketing is unique.<br
                      class="d-sm-none"
                    />We have been enabling businesses to<br />
                    effectively engage their customers.
                  </h2>
                </v-col>
                <v-col class="text-center" cols="12">
                  <v-dialog v-model="dialog" persistent max-width="300px">
                    <template v-slot:activator="{ on }">
                      <v-btn outlined v-on="on" class="white--text" x-large
                        >Let's get started <br />
                        with 10% discount</v-btn
                      >
                    </template>
                    <contact-form @close="dialog = false" />
                  </v-dialog>
                </v-col>
                <v-col cols="12" class="text-center">
                  <v-img
                    class="mx-auto"
                    src="@/assets/bubble.svg"
                    max-width="48px"
                    position="center"
                  />
                </v-col>
                <v-col cols="12">
                  <p
                    class="text-center lighten-4 font-weight-medium white--text promotion"
                  >
                    Effective marketing communication
                  </p>
                  <p
                    class="text-center lighten-4 font-weight-medium white--text promotion"
                  >
                    boost your business by 500%
                  </p>
                </v-col>
              </v-row>
            </v-container>
          </v-col>
        </v-row>
        <v-row
          v-if="smAndDown"
          class="mt-8 px-8"
          style="height: 100vh"
          justify="space-around"
          align-content="space-around"
        >
          <v-col cols="12">
            <v-img
              src="@/assets/hello.svg"
              max-height="48px"
              contain
              position="top left"
            />
            <h1>You have an <span>idea</span>.</h1>
          </v-col>
          <v-col cols="12">
            <h1>We will translate it into reality.</h1>
            <br />
            <h2 class="subtitle">
              Our approach to marketing is unique.<br class="d-sm-none" />We
              have been enabling businesses to<br />
              effectively engage their customers.
            </h2>
          </v-col>
        </v-row>
        <v-row v-if="smAndDown" align-content="start" class="px-8">
          <v-col class="text-center" cols="12">
            <v-dialog v-model="dialog" persistent max-width="300px">
              <template v-slot:activator="{ on }">
                <v-btn outlined v-on="on" class="white--text" x-large
                  >Let's get started <br />
                  with 10% discount</v-btn
                >
              </template>
              <contact-form @close="dialog = false" />
            </v-dialog>
          </v-col>
          <v-col cols="12" class="text-center">
            <v-img
              class="mx-auto"
              src="@/assets/bubble.svg"
              max-width="48px"
              position="center"
            />
          </v-col>
          <v-col cols="12">
            <p
              class="text-center lighten-4 font-weight-medium white--text promotion"
            >
              Effective marketing communication
            </p>
            <p
              class="text-center lighten-4 font-weight-medium white--text promotion"
            >
              boost your business by 500%
            </p>
          </v-col>
        </v-row>
      </v-container>
    </big-card>
  </div>
</template>

<script>
import BigCard from "@/components/BigCard";
import ContactForm from "./Form";
import Side from "../Side";

export default {
  components: { ContactForm, BigCard, Side },
  data() {
    return {
      dialog: false
    };
  },
  computed: {
    position() {
      if (this.$vuetify.breakpoint.mdAndDown) {
        return "top 30% left 30%";
      } else {
        return "top left";
      }
    },
    srcset() {
      const value = `${require("@/assets/bg-1920.png")} 1920w, ${require("@/assets/bg-1024.png")} 1024w, ${require("@/assets/bg-768.png")} 768w,`;
      return value;
    },
    smAndDown() {
      return this.$vuetify.breakpoint.xs;
    }
  }
};
</script>

<style lang="scss" scoped>
h1 {
  font-size: 5em;
  line-height: 1.1;
  text-transform: uppercase;
  color: white;
  word-wrap: break-word;
  span {
    color: black;
  }
}
h2.subtitle {
  font-size: 1.2em;
  line-height: 1.1;
}
p.promotion {
  font-size: 1.2em;
  margin-bottom: 1px !important;
}

@media screen and (min-width: 960px) {
  .home-content {
    margin: 0px;
    width: 100% !important;
    max-width: 100% !important;
  }
}

@media screen and (max-width: 600px) {
  h1 {
    font-size: 3.2em;
  }
  h2.subtitle {
    font-size: 1.5em;
  }
  p.promotion {
    font-size: 1em;
  }
}
</style>
