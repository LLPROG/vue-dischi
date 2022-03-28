<template>
  <div id="app">
    <header-dischi @onchange="setValueOption" @authorChange="setValueInput" />
    <main-dischi :selected-value="selected" :input-value="userInput"/>
  </div>
</template>

<script>
import HeaderDischi from './components/HeaderDischi.vue'
import MainDischi from './components/MainDischi.vue'

export default {
  name: 'App',
  components: {
    HeaderDischi,
    MainDischi
  },
  data () {
    return {
      selected: 'All',
      userInput: ''
    }
  },
  methods: {
    setValueOption (element) {
      this.selected = element
      console.log(element)
    },
    setValueInput (element) {
      this.userInput = element
      console.log(element)
    }
  }
}

</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import './assets/style.scss';
</style>
