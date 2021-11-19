<template>
  <Nav userName="userName" />
  <router-view/>
</template>

<script>
import Nav from './components/Nav.vue'
export default {
  components: {
    Nav
  },
  data: function() {
    return {
      userName: 'kira'
    }
  }
}
</script>

<style>
body{
  margin:0px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin:0;
  padding: 0;

}
.flex{
  display: flex;
}

</style>
