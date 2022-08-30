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
    async addFurniture(furniture){
      const res = await fetch("https://62ab736abd0e5d29af10bde6.mockapi.io/furnitures", {
        method: "POST",
        headers:{
          "Content-type": "application/json"
        },
        body: JSON.stringify(furniture)
      })

      const data = await res.json();
      this.pets = [...this.furnitures, data]
    },
    async removeFurniture(id){
      if (confirm("Are you sure tou want to remove this furniture?")){
        const res = await fetch(`https://62ab736abd0e5d29af10bde6.mockapi.io/furnitures/${id}`,
          {
            method: "DELETE",
          }
        );

        res.status === 200 ? (this.furnitures = this.furnitures.filter((furniture) => furniture.id !== id))
        : alert("Delete failed!");
      }
    },
    async addFavorite(id){
      const addFavorite = await this.fetchFurniture(id)
      const updatedFavorite = {
        ...addFavorite, isFavorite: !addFavorite.isFavorite
      }

      const res = await fetch(`https://62ab736abd0e5d29af10bde6.mockapi.io/furnitures/${id}`, {
        method: "PUT",
        headers: {
          "Content-type": "application/json"
        },
        body: JSON.stringify(updatedFavorite)
      });

      const data = await res.json()

      this.furnitures = this.furnitures.map((furniture) =>
      furniture.id === id? {...furniture, isFavorite: data.isFavorite} : furniture)
    },
    async fetchFurnitures() {
      const res = await fetch(
        "https://62ab736abd0e5d29af10bde6.mockapi.io/furnitures"
      );
      const data = await res.json();
      return data
    },
    async fetchFurniture(id){
      const res = await fetch(
        `https://62ab736abd0e5d29af10bde6.mockapi.io/furnitures/${id}`
      );
      const data = await res.json();
      return data
    }
  },
  data() {
    return {
      furnitures: [],
    };
  },
  async created(){
    this.furnitures = await this.fetchFurnitures();
  }
};
</script>
