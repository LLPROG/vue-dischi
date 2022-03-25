<template>
  <div class="my-card col">
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
.my-card {
  background-color: #2E3A46;
  // max-width: calc(100% / 5 - 2rem);
  height: 28rem;

  padding: 1rem;
  text-align: center;
  img {
    width: 100%;
    height: 50%;
  }

  h1 {
    color: white;
    font-size: 1.8em;
  }

  p {
    color: #767D7A;
  }
}
</style>
