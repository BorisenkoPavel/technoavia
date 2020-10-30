<template>
  <div id="app">
    <fruits />
  </div>
</template>

<script>
import Fruits from './components/Fruits.vue'

export default {
  name: 'App',
  components: {
    Fruits
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
  * {
    box-sizing: border-box;
  }
  html, body  {
    height: 100%;
  }
  body {
    background: #79C578;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: Roboto;
  }
</style>
