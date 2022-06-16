<template>
  <!-- <div class="home"></div> -->
  <AddFurniture @add-furniture="addFurniture" />
  <Furnitures @remove-furniture="removeFurniture" @add-favorite="addFavorite" :furnitures="furnitures" />
</template>

<script>
import Furnitures from "../components/Furnitures"
import AddFurniture from "../components/AddFurniture"

export default {
  name: 'HomeView',
  components: { AddFurniture, Furnitures },
  methods: {
    addFurniture(furniture) {
      this.furnitures = [...this.furnitures, furniture];
    },
    removeFurniture(id) {
      if (confirm("Are you sure you want to remove this furniture?")) {
        this.furnitures = this.furnitures.filter((furniture) => furniture.id !== id)
      }
    },
    addFavorite(id){
      this.furnitures = this.furnitures.map((furniture) => 
      furniture.id === id ? {...furniture, isFavorite: !furniture.isFavorite} : furniture
      );
    },
  },
  data() {
    return {
      furnitures: [],
    };
  },
  created(){
    this.furnitures = [
        {
          id: 1,
          name: "Timber Charme Tan Sofa",
          price: "300$",
          url: "https://images.unsplash.com/photo-1540574163026-643ea20ade25?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80",
          isFavorite: false
        },
        {
          id: 2,
          name: "Esse Dark Oak Counter Stool",
          price: "150$",
          url: "https://images.unsplash.com/photo-1540809799-5da9372c3f64?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=724&q=80",
          isFavorite: true
        },
        {
          id: 3,
          name: "Seno Walnut Dining Table",
          price: "400$",
          url: "https://images.unsplash.com/photo-1593512828202-a5b036b628a9?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80",
          isFavorite: true
        },
    ]
  }
};
</script>
