<template>
    <div class="list-item">
        <h2>{{catName}}</h2>
        <hr>
        <div>
            <li 
            v-for="item in items" 
            :key='item.id'
            class="item"
            >
                <div class="flex">
                    <input type="checkbox" name="status" id="{{item.id}}"
                    @click="check(item.id)"
                >
                <p :class='{done:item.status}'>{{ item.name }}</p>
                </div>   
                <div v-if="item.sub[0]" class="sub-lists">
                    <div v-for="sub  in  item.sub" :key='sub.id' class="sub-list flex">
                        <input 
                        type="checkbox" name="status" id="{{sub.id}}"
                        @click="subCheck(item, sub)"
                        >
                        <p :class='{done:sub.status}'> {{ sub.name }}</p>
                        
                    </div>
                </div>
            </li>
        </div>
    </div>
</template>

<script>
export default {
    name: "ListItem",
    props: {
        items: [],
        catName: String
    },
    methods: {
        check (id) {
            let item = this.items.filter(item => item.id == id )[0]
            item.status = !item.status;
        },
        subCheck (item, sub){
            let targetItem = this.items.filter(item => item.id == item.id )[0]
            let subItem = targetItem.sub.filter(subItem => subItem == sub )[0]
            subItem.status = !subItem.status
        }
        
    }
}
</script>




<style>
.done{
    color:rgb(86, 214, 96);
    text-decoration: line-through;
}
.sub-lists{
    margin-left:30px ;
}
.item{
    list-style: none;
}
input{
    margin-right:7px;
}
</style>