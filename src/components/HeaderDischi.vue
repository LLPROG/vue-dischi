<template>
  <header>
    <selector-genre @onchange="onchange" />
    <input-author  @authorChange="authorChange"/>
  </header>
</template>

<script>
import SelectorGenre from './SelectorGenre.vue'
import InputAuthor from './InputAuthor.vue'

export default {
  name: 'HeaderDischi',
  components: {
    SelectorGenre,
    InputAuthor
  },
  methods: {
    onchange (selected) {
      this.$emit('onchange', selected)
    },
    authorChange (userInput) {
      this.$emit('authorChange', userInput)
    }
  }
}
</script>

<style lang="scss" scoped>
header {
  width: 100%;
  height: 8rem;
  background-color: #2E3A46;
}
</style>
