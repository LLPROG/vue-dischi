<template>
  <div id="app">
    <header-dischi @onchange="setValue"/>
    <main-dischi :selected-value="selected"/>
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
      selected: 'All'
    }
  },
  methods: {
    setValue (element) {
      this.selected = element
      console.log(element)
    }
  }
}

</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import './assets/style.scss';

</style>
