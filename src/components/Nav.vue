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
