<template>
    <main class="main">
      <div class="container">
        <ul class="characters">

          <Character v-for="element in store.characters" :key="element.id" :character="element" />
  
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
          info: {},
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
            .get('https://db.ygoprodeck.com/api/v7/cardinfo.php')
            .then((res) => {
              this.store.characters = res.data.results
            })
        }
      },
      created() {
        console.log('store',this.store)
        this.fetchCharacters()
      },
    }
  </script>
  
  <style lang="scss" scoped>
  .main {
    padding: 100px 0;
  }
  .characters {
    display: grid;
    gap: 40px;
    grid-template-columns: repeat(5,1fr);
  }
  </style>