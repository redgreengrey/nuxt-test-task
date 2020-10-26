<template lang="pug">
  v-card
    v-card-text
      v-form(@submit.prevent="onSubmit")
        v-text-field(
          :value="current.id"
          label="ID"
          readonly
        )
        User(
          v-model="current.userId"
        )
        v-text-field(
          v-model="current.title"
          label="Title"
        )
        v-textarea(
          v-model="current.body"
          label="Text"
        )
        v-btn(
          color="purple"
          large
          type="submit"
        ) Save

</template>

<script>
import User from '~/components/User'

export default {
  async asyncData({ $axios, route }) {
    const original = await $axios.$get(`https://jsonplaceholder.typicode.com/posts/${route.params.id}`)
    
    return { original, current: JSON.parse(JSON.stringify(original)) }
  },

  data: () => ({
    original: {},
    current: {},
    userId: null
  }),

  methods: {
    onSubmit() {
      console.log(this.current)
    },
    setUserId(value) {
      this.current.userId = value
    }
  },

  components: {
    User
  }
}
</script>

<style lang="sass">
</style>
