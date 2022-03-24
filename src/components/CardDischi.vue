<template>
  <div class="card col-6 col-md-4 col-lg-2">
    <img class="fluid" :src="cardsData.image" :alt="cardsData.title">
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
