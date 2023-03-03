<template>
    <header class="main-header">
      <div class="container">
        <h1>{{ title }}</h1>
      </div>
    </header>
  </template>
  
  <script>
    export default {
      data() {
        return {
          title: 'YU-GI-OH Api'
        }
      }
      
    }
  </script>
  
  <style lang="scss" scoped>
  @use '../style/partials/variables' as *;
  .main-header {
    text-align: center;
    font-size: 20px;
    padding: 1rem 0;
  }
  </style>