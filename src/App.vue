<template>
  <Nav user-name='kirubel'/>
  <Aside/>
  <ListItem :items='data'/>
</template>

<script>

import Nav from './components/Nav'
import Aside from './components/Aside'
import ListItem from './components/ListItem'

let data = [
      {
        id:2,
        name:'coding'
      },
      {
        id:2,
        name:'eating food'
      }]

export default {
  name: 'App',
  components: {
    Nav,
    Aside,
    ListItem
  },
  data: function() {
    return{
      data
    }
  }
}
</script>

<style >

</style>
