<template>
  <div class="back">
    <div v-if="cards == null" class="loader">
      <!-- loader -->
    </div>
    <div v-else class="container">
      <div class="cards row row-cols-6">
        <CardDischi v-for="card in setValue" :key="card.id"
          :cards-data="card"
        />
      </div>
    </div>
  </div>
</template>

<script>
import CardDischi from './CardDischi.vue'
import axios from 'axios'
export default {
  name: 'MainDischi',
  props: {
    selectedValue: String,
    inputValue: String
  },
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
          console.log(response.data)
          this.cards = response.data.response.map((el) => {
            return {
              image: el.poster,
              title: el.title,
              author: el.author,
              year: el.year,
              genre: el.genre
            }
          })
        })
    }, 1000)
  },
  computed: {
    setValue () {
      if (this.selectedValue === 'All') {
        return this.cards.filter(obj => obj.author.toLowerCase().includes(this.inputValue.toLowerCase()))
      } else {
        return this.cards.filter(obj => obj.genre === this.selectedValue && obj.author.toLowerCase().includes(this.inputValue.toLowerCase()))
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.back {
  background-color: #1E2D3B;
  min-height: 100vh;
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
  justify-content: center;
  flex-wrap: wrap;
  gap: 2rem;
}
</style>
