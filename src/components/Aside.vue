<template>
    <aside>
        <ul>
            <li>
                add item
            </li>
            <li>
                manage items
            </li>
            <li>
                change account
            </li>
            <li>
                pro version
            </li>
        </ul>
    </aside>
</template>

<script>
export default {
    name:"Aside"
}
</script>

<style scoped>
aside{
    padding: 10px;
    border-right: 1px solid #2c3e50;;
    
}
ul{
    padding: 0px;
}
li{
    list-style: none;
    padding:10px
}
</style>