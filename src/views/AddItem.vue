<template>
    <div class="add-item">
        <div class="name">
            <label for="name">Name</label>
            <input type="text" name="name" id="name" v-model="name" >
        </div>
        <div class="cat">
            <label for="cat">catagories</label>
            <input type="text" name="cat" id="cat" v-model="cat" >
        </div>
        <button @click="$emit('addItem', name, cat)">add</button>
    </div>
</template>
<script>
export default {
    name: 'AddItem',
    data: function ( ){
        return{
            name: '',
            cat: ''
        }
    }
    ,
    methods: {
        
    }
}
</script>

<style scoped>
.add-item{
    padding:15px;
    border: 1px solid #2c3e50;
    margin: 20px;
    width:400px;
    border-radius: 4px; 
}
label{
    min-width: 100px;
}
.name,.cat{
padding: 5px 3px;
display:flex;
}
label{
    margin-right: 20px;
    width: 100px
}
button{
    padding:2px 8px;
}
</style>