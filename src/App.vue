<template>
  <div id="app">
    <Header />
    <router-view/>
  </div>
</template>

<script>

import Header from '@/components/Header.vue';
export default {
  components: {
    Header
  }
}
</script>

<style lang="scss">
html, body, #app {
  box-sizing: border-box;
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>
