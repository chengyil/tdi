<template>
  <div>
    <div class="logo d-flex flex-column justify-space-around align-center">
      <v-img src="@/assets/logo.png" contain class="logo-img" />
      <p
        class="subtitle-1 text-center lighten-4 font-weight-bold"
        :class="{
          'white--text': !light,
          'grey--text': light,
          'text--darken-1': light
        }"
      >
        Creativity + Business Solution
      </p>
    </div>
    <v-list expand color="rgba(0,0,0,0)">
      <v-list-group
        v-for="group in sideItems"
        :key="group.title"
        v-model="group.active"
      >
        <template v-slot:activator>
          <v-list-item-content>
            <v-list-item-title
              v-text="group.title"
              :class="{ 'white--text': light }"
            />
          </v-list-item-content>
        </template>
        <v-list-item v-for="item in group.items" :key="item" @click="handle">
          <v-list-item-content>
            <v-list-item-subtitle
              v-text="item"
              :class="{ 'white--text': light }"
            />
          </v-list-item-content>
        </v-list-item>
      </v-list-group>
    </v-list>
  </div>
</template>

<script>
export default {
  methods: {
    handle() {}
  },
  props: {
    light: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      sideItems: [
        {
          active: true,
          title: "Prints",
          items: [
            "Flyer & Poster",
            "Name Card",
            "Business Stationary",
            "Banner & Canvas",
            "Sticker",
            "Digital Large Format",
            "T-Shirts & Fabrics"
          ]
        },
        {
          title: "Digital",
          items: [
            "Website Design & Development",
            "E-Commerce",
            "Digital Marketing (SEO / SEM)",
            "Landing Page",
            "WIX / Shopify",
            "Social Media"
          ]
        },
        {
          title: "Creativity",
          items: [
            "Branding",
            "Communication Design",
            "Industrial Design",
            "Copywriting & Translation"
          ]
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
div.logo {
  height: 200px !important;
  .logo-img {
    width: 65%;
  }
}
.v-list-group {
  padding-bottom: 5px;
  border-top: 1px solid white;
}

.v-list-item {
  min-height: 15px !important;
}
.v-list-item__content {
  padding-top: 5px !important;
  padding-bottom: 5px !important;
}

.v-list-item--active {
  .v-list-item__title {
    color: lightblue;
  }
}
</style>
