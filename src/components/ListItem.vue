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
                    <div v-for="item  in  item.sub" :key='item.id' class="sub-list flex">
                        <input type="checkbox" name="status" id="{{item.id}}">
                        {{ item.name }}
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
            console.log(id, this.items)
            let task = this.items.filter(task => task.id == id )[0]
            console.log(task)
            task.status = !task.status;
        },
        
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