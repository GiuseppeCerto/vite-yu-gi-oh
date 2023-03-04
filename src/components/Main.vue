<template>
    <main class="main">
      <div class="container">
        <ul class="characters">

          <Character v-for="(element,i) in store.characters" :key="i" :character="element" />
  
        </ul>
      </div>
    </main>
  </template>
  
  <script>
    import axios from 'axios'
    import store from '../store'
    import Character from './Character.vue'
    export default {
      components: {
        Character
      },
      data() {
        return {
          store,
        }
      },
      computed: {
        characters() {
          return this.store.characters
        }
      },
      methods: {
        fetchCharacters() {
          axios
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
            .then((res) => {
              this.store.characters = res.data.data
            })
        }
      },
      created() {
        this.fetchCharacters()
      },
    }
  </script>
  
<style lang="scss" scoped>

.characters {
  display: grid;
  grid-template-columns: repeat(5,1fr);
}
</style>