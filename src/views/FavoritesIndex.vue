<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <div v-for="favorite in favorites">
      <router-link v-bind:to="`/recipes/${favorite.recipe_id}`">
        <h3> {{ favorite.recipe.name }} </h3>
        <h5> {{ favorite.recipe.alcoholic }} </h5>
      </router-link>
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
  },
};
</script>
