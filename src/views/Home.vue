<template>
<div class="home">


  <Aside/>
  <div class="main">
    <add-item @add-item="addItem" />
    <div
      v-for='cat in newItems'
      :key="cat.name"
    >
      <ListItem :items='cat.data' :catName="cat.name"/> 
    </div>
    
  </div>
</div>
</template>

<script>
// @ is an alias to /src
let data = [
  {
    id: 1,name: 'learn vue',status: false,cat:'work',sub: [{id:4,name: 'build 2 apps with vue',status: false}]
  },
  {
    id: 2,name: 'build the amzon clone',status: false,cat:'work',sub: []},
  {
    id: 3,name: '100 push up',status: false,cat:'sport ',sub: []
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
          id: 4,
          name,
          status: false,
          cat,
          sub: [
          ]
        }
      let status = false
      this.data.map(oldItem => {
        if(oldItem.name == newItem.name){
          status = true
        }else{
          status = false
        }
      })
      
      console.log(status, 'this is tatus')
      if (status == false){
        this.data.push(newItem)
        this.sort()
      }
      
    },

    sort (){
            let cats = []
            let newItems = []
            this.data.map(item => {
              
              if(cats.indexOf(item.cat) == -1){
                newItems.push(
                  {'name':item.cat,'data':[item]}
                  )
                cats.push(item.cat)
              }
              else{
                newItems.filter(function(elem){
                  if(elem.name == item.cat){
                    elem.data.push(item)
                  }
                })  
              }
            })
            this.newItems = newItems
            
        }
  },
  created(){
      this.sort()
  }
}
</script>

<style>
.home{
  display:flex;
}
</style>