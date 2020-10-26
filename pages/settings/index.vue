<template lang="pug">
  section
    v-card(
      class="mx-auto my-6"
      max-width="500"
    )
      v-card-text
        h3.ml-8 Выберите тему:
        ol.mt-6.mb-6.d-flex.justify-space-between
          
          li
            v-btn(
            @click="setLightTheme"
            class="mx-2"
            light
          ) Светлая
          li
            v-btn(
            @click="setDarkTheme"
            class="mx-2"
            dark
          ) Тёмная

</template>

<script>
export default {
  methods: {
    setLightTheme() {
      this.$vuetify.theme.dark = false
    },
    setDarkTheme() {
      this.$vuetify.theme.dark = true
    }
  }
}
</script>

<style lang="sass" scoped>
li
  list-style: none
</style>

