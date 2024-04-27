<template>
    <div class="container">
        <div v-for="groceries of groceryItemsList" :key="groceries.groceries_id">
            <GroceryItem :groceries = groceries />
        </div>
    </div>
</template>

<script>
import GroceryItem from "./GroceryItem.vue"; 
    export default{
        name:"GroceryItemsList",
        components:{
            GroceryItem
        },
        props:{
            groceryItemsList: Array
        }
    }
</script>

<style scoped>
    .container{
        margin-top:10px;
    }
</style>