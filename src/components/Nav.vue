<template>
    <nav>
        <div class="logo">
            <img src="@/assets/hagre.svg" alt="">
        </div>
        <div class="account">
            {{userName}}
        </div>
    </nav>
</template>


<script>
export default {
    name: 'Nav',
    props:{
        userName: String
    }
}
</script>

<style scoped>
nav {
    padding: 10px;
    margin: 0;
    display: flex;
    background:#2c3e50;
}
img{
    height: 60px
}
account{
    color: rgb(255, 255, 255);
}
</style>