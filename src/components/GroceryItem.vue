<template>
    <div class="container">
        <h2 id="grocery-title" :style="{backgroundColor: this.getBackgroundColour(groceries.grocery_category)}">{{groceries.grocery_category}}</h2>
        <div class="grocery-container">
            <div v-for="groceryItem of groceries.grocery_items" :key="groceryItem.item_id">
                <img :src=groceryItem.item_image alt=groceryItem.item_name class="grocery-img"/>
                <h3>{{groceryItem.item_name}}</h3>
                <h3>$ {{groceryItem.item_price}}</h3>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        name:"GroceryItem",
        props:{
            groceries:Object
        },
        methods:{
            getBackgroundColour(groceryItem){
                switch(groceryItem){
                    case "Fruits" :return "#8ecae6";
                    case "Pulses" :return "#ffc300";
                    case "Vegetables": return "#83c5be";
                    case "Dairy": return "#f4acb7";
                    case "Grains": return "#efc3e6";
                }
            }
        }
    }
</script>

<style scoped>
 .container{
    border:transparent;
    border-radius:5px;
    box-shadow:0 4px 8px 0 rgba(0,0,0,0.2),0 6px 20px 0 rgba(0,0,0,0.19);
 }
 #grocery-title{
    text-align:center;
    background-color:#ffb3c1;
    padding:10px;
 }
 .grocery-container{
    display:flex;
    justify-content:space-evenly;
    align-items:center;
 }
 .grocery-img{
    width:70px;
    height:70px;
 }
</style>