<template>
    <div class="container">
        <input @keyup.enter="$emit('onSearch')" class="search" type="text" v-model="store.search" placeholder="Filter by name">
    </div>
  </template>

  <script>
  import store from '../store'
  export default {
    data() {
      return {
        store,
      }
    },
  }
</script>

<style lang="scss" scoped>

</style>