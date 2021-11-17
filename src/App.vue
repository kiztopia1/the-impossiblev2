<template>
  <Nav user-name='kirubel'/>
  <Aside/>
  <ListItem :items='data'/>
  <AddItem @add-item='addItem'/>
</template>

<script>

import Nav from './components/Nav'
import Aside from './components/Aside'
import ListItem from './components/ListItem'
import AddItem from './components/AddItem'

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
    ListItem,
    AddItem
  },
  data: function() {
    return{
      data
    }
  },
  methods:{
    addItem (name, cat) {
            let item = {
                name: name,
                id: 33,
                cat: cat,
                sub: []
            }
            this.data.push(item)
            console.log(item)
        }
  }
}
</script>

<style >
.flex{
  display: flex;
}
</style>
