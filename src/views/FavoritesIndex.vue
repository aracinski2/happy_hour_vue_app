<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="favorite in favorites">
      <router-link v-bind:to="`/recipes/${favorite.recipe_id}`">
        <h3> {{ favorite.recipe.name }} </h3>
        <h5> {{ favorite.recipe.alcoholic }} </h5>
      </router-link>
        <button v-on:click="favoritesDestroy()">Remove</button>
    </div>
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Welcome to your favorites!",
      favorites: [],
    };
  },
  created: function () {
    this.favoritesIndex();
  },
  methods: {
    favoritesIndex: function () {
      console.log("favorites indexxx");
      axios.get("/api/favorites").then((response) => {
        console.log(response.data);
        this.favorites = response.data;
      });
    },
    favoritesDestroy: function () {
      console.log("In favorites destroy");
      console.log(this.$route.favorite);
      // var params = {
      //   id: this.,
      // };
      axios.delete("/api/favorites/" + this.$route).then((response) => {
        console.log(response.data);
        // var index = this.favorites.indexOf(this.currentFavorite);
        // console.log(index);
        // this.favorites.splice(index, 1);
      });
    },
  },
};
</script>
