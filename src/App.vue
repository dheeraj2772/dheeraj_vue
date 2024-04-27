<template>
  <GroceryHeader/>
  <GroceryItemsList :groceryItemsList = groceryItemsList />
</template>

<script>
import GroceryHeader from "./components/GroceryHeader.vue";
import GroceryItemsList from "./components/GroceryItemsList.vue";

export default {
  name: "App",
  components:{
    GroceryHeader,
    GroceryItemsList
  },
  data(){
    return{
      groceryItemsList:[]
    }
  },
  methods:{
    async fetchGroceryItems(){
      const res = await fetch("https://grocery-c9l4.onrender.com/api");
      const groceryData = await res.json();
      console.log(groceryData[0].groceries);
      return groceryData[0].groceries;
    }
  },
  async created(){
    this.groceryItemsList = await this.fetchGroceryItems();
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Merienda:wght@300..900');

  *{
    font-family: "Merienda", cursive;
  }
</style>
