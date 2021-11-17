<template>
  <Nav user-name='kirubel'/>
  <Aside/>
</template>

<script>

import Nav from './components/Nav'
import Aside from './components/Aside'
export default {
  name: 'App',
  components: {
    Nav,
    Aside
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
