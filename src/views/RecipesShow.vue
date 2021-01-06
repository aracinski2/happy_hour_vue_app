<template>
  <div class="recipes-show">
    <h1>{{ recipe.name }}</h1>
    <h5>{{ recipe.alcoholic }}</h5>
    <h4>{{ recipe.instructions }}</h4>

    <!-- <div v-for="ingredient in ingredients"> -->
    <!-- </div> -->
     <h3>Ingredients:</h3>
     <div v-for="(ingredient, index) in recipe.ingredients">

        <h5>{{ ingredient.name }}: {{ recipe.measurements[index].measurement }}</h5>
    </div>
    <button v-on:click="favoritesCreate()">Save!</button>
    
    
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Look at this super specific recipe!",
      recipe: {},
    };
  },
  created: function () {
    this.recipeShow();
  },
  methods: {
    recipeShow: function () {
      console.log("recipes showwww");
      console.log(this.$route.params.id);
      axios.get("/api/recipes/" + this.$route.params.id).then((response) => {
        console.log(response.data);
        this.recipe = response.data;
      });
    },
    favoritesCreate: function () {
      console.log("favorite created!");
      axios.post("/api/favorites").then((response) => {
        console.log(response.data);
        this.favorite = response.data;
      });
    },
  },
};
</script>