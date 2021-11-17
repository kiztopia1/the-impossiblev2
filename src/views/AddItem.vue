<template>
    <div class="add-item">
        <div>
            <label for="name">Name</label>
            <input type="text" name="name" id="name" v-model="name" >
        </div>
        <div>
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