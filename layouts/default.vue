<template lang="pug">
  v-app#inspire
    Header(
      @toggleMenu="toggleMenu"
    )
    Nav(
      :drawerLeft="drawerLeft"
    )
    v-main
      nuxt
    Footer

</template>

<script>
import Header from '~/components/layout/Header'
import Nav from '~/components/layout/Nav'
import Footer from '~/components/layout/Footer'

export default {
  components: {
    Header,
    Nav,
    Footer,
  },

  data: () => ({
    drawerLeft: true,
  }),

  methods: {
    toggleMenu() {
      this.drawerLeft = !this.drawerLeft
    }
  },

  created () {
    this.$vuetify.theme.dark = true
  },
}
</script>

<style lang="sass">
</style>
