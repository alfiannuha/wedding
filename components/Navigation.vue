<template>
  <div>
    <v-bottom-navigation grow fixed v-model="value" color="#6D4C41">
      <nuxt-link
        style="height:55px;color: #6D4C41"
        class="mx-1"
        v-for="(item, index) in menu"
        :key="index"
        :to="item.link">
        <v-btn>
          {{ item.label }}
          <v-icon color="brown">{{ item.icon }}</v-icon>
        </v-btn>
      </nuxt-link>
    </v-bottom-navigation>
  </div>
</template>

<script>
export default {
  data() {
    return {
      value: 0,
      menu: [
        {
          label: "Home",
          icon: "mdi-home",
          link: "/"
        },
        {
          label: "Acara",
          icon: "mdi-clock",
          link: "#timeline"
        },
        {
          label: "Gallery",
          icon: "mdi-image",
          link: "#gallery"
        },
        {
          label: "Lokasi",
          icon: "mdi-map",
          link: "#lokasi"
        }
      ],
    }
  }
}
</script>

<style>

</style>