<template lang="pug">
  v-app-bar(
    app
    clipped-left
    color="dark"
    dark
  )
    v-app-bar-nav-icon(@click.stop="toggleMenu")
    v-toolbar-title
      n-link(
        class="white--text"
        to="/"
      ) Test task
    v-spacer

</template>

<script>
export default {
  props: {
    drawerLeft: Function
  },
  methods: {
    toggleMenu() {
      this.$emit("toggleMenu")
    }
  },
}
</script>

<style lang="sass">

</style>
