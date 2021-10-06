<template>
  <v-app>
    <Header/>
    <v-sheet>
      <Nuxt />
    </v-sheet>
    <!-- <v-main light> -->
    <!-- </v-main> -->
    <v-fab-transition>
      <v-btn
        v-scroll="onScroll"
        v-show="fab"
        elevation="3"
        class="mb-13"
        fab
        dark
        fixed
        bottom
        right
        color="#6D4C41"
        to="/"
        @click="$vuetify.goTo('#app', {duration: 500, offset: 0})">
        <v-icon>mdi-chevron-up</v-icon>
      </v-btn>
    </v-fab-transition>
    <Navigation v-if="$vuetify.breakpoint.name === 'xs'"/>
  </v-app>
</template>

<script>
import Header from "~/components/Header.vue"
import Navigation from "~/components/Navigation.vue"
export default {
  data () {
    return {
      fab: false,
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  },
  methods: {
    onScroll (e) {
      if (typeof window === 'undefined') return
      const top = window.pageYOffset || e.target.scrollTop || 0
      this.fab = top > window.innerHeight-100
    }
  }
  
}
</script>
