<template>
  <div>
    <label for="input">
      cerca autore
      <input type="text" @input="$emit('authorChange', userInput)" v-model="userInput">
    </label>
  </div>
</template>

<script>
export default {
  name: 'InputAuthor',
  data () {
    return {
      userInput: ''
    }
  }
}
</script>

<style lang="scss" scoped>
label {
  position: relative;
  top: 10%;
  left: 50%;
  transform: translate(-50%);
  color: white;
  text-transform: uppercase;
  margin-top: 1rem;
}
</style>
