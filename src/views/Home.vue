<template>
<div class="home">


  <Aside/>
  <div class="main">
    <add-item @add-item="addItem" />

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
    cat:'',
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
    cat:'',
    sub: []
  },
  {
    id: 3,
    name: 'coading',
    status: false,
    cat:'',
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
      data,
      newItems: [],
    }
  },
  components: {
    AddItem,
    Aside,
    ListItem
  },
  methods: {
    addItem (name, cat){
      
      let newItem = {
          id: 7,
          name,
          status: false,
          cat,
          sub: [
          ]
        }
      this.data.push(newItem)
    }
  },
  created(){
    let cats = []
    let newItems = []
    this.data.map(item => {
      if(cats.indexOf(item.cat) == -1){
        newItems.push({name:item.cat,data:item})
      }
      else{
        newItems.map(cat => {
          if(cat.name == item.cat){
            cat.push(item)
          }
        })
      }
    })
    this.newItems == newItems
  }
}
</script>
<style>
.home{
  display:flex;
}
</style>