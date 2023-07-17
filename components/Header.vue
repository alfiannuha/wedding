<template>
  <div>
    <v-app-bar
      v-if="$route.name !== 'faqlite' && $route.name !== 'privacylite' && $route.name !== 'aboutlite'"
      app
      elevation="0"
      fixed
      :class="$route.name !== 'fiture' && $route.name !== 'faq' && $route.name !== 'privacy' && $route.name !== 'about' &&  $route.name !== 'help' ? 'header' : ''">
      <v-container>
        <v-row justify="center" align="center" class="hidden-md-and-down">
          <v-col cols="9" class="d-flex align-center justify-left">
            <nuxt-link to="/" style="text-decoration: none">
            <div class="header-title text-center">
              Nuha & Nabila
            </div>
            </nuxt-link>
            <nuxt-link
              style="text-decoration: none"
              v-for="(item, index) in menu"
              :key="index"
              :to="item.link"
              :class="index === 0 ? 'ml-12' : ''"
            >
              <v-card-title
                class="body-2 menu cursor-pointer text-first hover-link"
              >
                {{ item.label }}
              </v-card-title>
            </nuxt-link>
          </v-col>
        </v-row>
        <v-row justify="center" align="center" class="hidden-lg-and-up">
          <v-col cols="10" style="padding: 0 0 1rem">
            <nuxt-link to="/">
              <div class="header-title text-center">
                Nuha & Nabila
              </div>
            </nuxt-link>
          </v-col>
        </v-row>
      </v-container>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menu: [
        {
          label: "Acara",
          icon: "mdi-clock",
          link: "#timeline"
        },
        {
          label: "Gallery",
          link: "#gallery"
        },
        {
          label: "Lokasi",
          link: "#lokasi"
        }
      ],
      sosmed: [
        require("@/assets/sosmed/ic_share_fb.svg"),
        require("@/assets/sosmed/ic_share_ig.svg"),
        require("@/assets/sosmed/ic_share_tw.svg")
      ]
    };
  },
  computed: {
  },
  mounted() {
    const debounce = fn => {
      let frame;
      return (...params) => {
        if (frame) {
          cancelAnimationFrame(frame);
        }
        frame = requestAnimationFrame(() => {
          fn(...params);
        });
      };
    };
    const storeScroll = () => {
      document.documentElement.dataset.scroll = window.scrollY;
    };
    document.addEventListener("scroll", debounce(storeScroll), {
      passive: true
    });
    storeScroll();
  },
  methods: {}
};
</script>

<style scoped>
.header-title {
  font-family: 'Kaushan Script', cursive !important;
  font-size: 30px;
  color: #6D4C41
}
.header {
  background-color: transparent !important;
  /* background-color: #EFEBE9 !important; */
}
html:not([data-scroll="0"]) .header {
  background-color: #FFFFFF !important;
}
</style>