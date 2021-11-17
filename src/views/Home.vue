<template>
<div class="home">


  <Aside/>
  <div class="main">
    <add-item/>
    <ListItem :items="data" cat-name="main"/>
  </div>
</div>
</template>

<script>
// @ is an alias to /src
let data = [
  {
    id: 1,
    name: 'coading',
    status: false,
    sub: [
      {
        id:4,
        name: '100 lines',
        status: false
      }
    ]
  },
  {
    id: 2,
    name: 'coading',
    status: false,
    sub: []
  },
  {
    id: 3,
    name: 'coading',
    status: false,
    sub: []
  },
]
import Aside from '@/components/Aside'
import AddItem from '@/views/AddItem'
import ListItem from '../components/ListItem.vue'
export default {
  name: 'Home',
  data: function (){
    return{
      data
    }
  },
  components: {
    AddItem,
    Aside,
    ListItem
  }
}
</script>
<style>
.home{
  display:flex;
}
</style>