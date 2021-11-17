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
        id:1,
        name:'coding',
        status: false,
        sub: [
          {
            id:3,
            name:'15 commits',
            status: false
          }
        ]
      },
      {
        id:2,
        name:'eating food',
        status: false,
        sub: []
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
.flex{
  display: flex;
}
</style>
