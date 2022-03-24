<template>
  <div class="back">
    <div class="cards container">
      <CardDischi v-for="card in cards" :key="card.id"
        :cards-data="card"
      />
    </div>
  </div>
</template>

<script>
import CardDischi from './CardDischi.vue'
import axios from 'axios'
export default {
  name: 'MainDischi',
  data () {
    return {
      cards: null
    }
  },
  components: {
    CardDischi
  },
  created () {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((response) => {
        console.log(this.cards)
        this.cards = response.data.response.map((el) => {
          return {
            image: el.poster,
            title: el.title,
            author: el.author,
            year: el.year
          }
        })
      })
    console.log(this.cards)
  }
}
</script>

<style lang="scss" scoped>
.back {
  background-color: #1E2D3B;
  padding: 5rem 0;

}
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
}
</style>
