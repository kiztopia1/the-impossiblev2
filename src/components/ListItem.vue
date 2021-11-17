<template>
    <div class="list-item">
        {{catName}}
        <div>
            <li 
            v-for="item in items" 
            :key='item.id'
            >
                <p>{{ item }}</p>
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
    }
}
</script>