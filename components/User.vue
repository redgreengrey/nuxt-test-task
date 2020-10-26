<template lang="pug">
  div.d-flex
    v-autocomplete(
      :items="labels"
      search-input
      label="User"
      placeholder="Type username or id"
      @input="handleInput"
      :value="value"
    )

</template>

<script>
export default {
  props: {
    value: {
      type: Number
    }
  },
  data() {
    return {
      labels: [],
      content: this.value
    }
  },
  fetch() {
    return this.$axios.$get(
      'https://jsonplaceholder.typicode.com/users'
    )
      .then(res => this.labels = res.map(u => ({ text: u.username + " - " + u.id, value: u.id })))
  },
  methods: {
    handleInput (value) {
      this.$emit("input", value)
    }
  }

}
</script>

<style>

</style>
