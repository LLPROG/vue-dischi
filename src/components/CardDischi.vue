<template>
  <div class="card">
    <img :src="cardsData.image" :alt="cardsData.title">
    <h1 v-if="cardsData.title">{{ cardsData.title }}</h1>
    <p v-if="cardsData.author">{{ cardsData.author }}</p>
    <p v-if="cardsData.year">{{ cardsData.year }}</p>
  </div>
</template>

<script>
export default {
  name: 'CardDischi',
  props: {
    cardsData: Object
  }
}
</script>

<style lang="scss" scoped>

</style>
