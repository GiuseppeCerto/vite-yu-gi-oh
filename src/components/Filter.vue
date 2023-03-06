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
    .container{
        display: flex;
        justify-content: center;
    }
    .search{
        width: 300px;
        height: 40px;
        background-color: grey;
        border: 1px solid yellow;
        margin-bottom: 20px;
    }
    .search::placeholder{
        color: black;
        font-size: 18px;
    }
</style>