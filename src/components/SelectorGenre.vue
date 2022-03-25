<template>
  <div>
    <label for="select">
      seleziona il genere
      <select @change="$emit('onchange', selected)" name="genre" id="genre" v-model="selected">
        <option value="All">All</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
        <!--  -->
      </select>
    </label>
  </div>
</template>

<script>
export default {
  name: 'SelectorgGenre',
  data () {
    return {
      selected: 'All'
    }
  }
}
</script>

<style lang="scss" scoped>
label {
  position: relative;
  left: 50%;
  transform: translate(-50%);
  color: white;
  text-transform: uppercase;
  margin-top: 1rem;
}
</style>
