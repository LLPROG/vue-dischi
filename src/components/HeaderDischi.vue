<template>
  <header>
    <selector-genre @onchange="onchange" />
  </header>
</template>

<script>
import SelectorGenre from './SelectorGenre.vue'
export default {
  name: 'HeaderDischi',
  components: {
    SelectorGenre
  },
  methods: {
    onchange (selected) {
      this.$emit('onchange', selected)
      console.log(selected)
    }
  }
}
</script>

<style lang="scss" scoped>
header {
  width: 100%;
  height: 4rem;
  background-color: #2E3A46;
}
</style>
