<template>
  <div class="back">
    <div v-if="cards == null" class="loader"></div>
    <div v-else class="cards container">
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
    setTimeout(() => {
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
    }, 3000)
  }
}
</script>

<style lang="scss" scoped>
.back {
  background-color: #1E2D3B;
  padding: 5rem 0;
  .loader {
    position: relative;
    top: 0;
    left: 50%;
    transform: translate(-50%);
    display: inline-block;
    width: 80px;
    height: 80px;
    &:after {
      content: " ";
      display: block;
      width: 64px;
      height: 64px;
      margin: 8px;
      border-radius: 50%;
      border: 6px solid #fff;
      border-color: #fff transparent #fff transparent;
      animation: spin 1.2s linear infinite;
    }
  }
}
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 2rem;
}
</style>
