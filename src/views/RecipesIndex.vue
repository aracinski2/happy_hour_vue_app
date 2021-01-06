<template>
  <div class="recipes-index">
    <h1>{{ message }}</h1>
    <div v-for="recipe in recipes">
      <router-link v-bind:to="`/recipes/${recipe.recipe_id}`">
      <h3>{{ recipe.name }}</h3>
      </router-link>
      <br>
      <!-- <h5>{{ recipe.alcoholic }}</h5> -->
    </div>
    

    <!-- <div v-for="ingredient in ingredients"> -->
    <!-- </div> -->
   

    
    
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Look at all these awesome recipes!",
      recipes: [],
    };
  },
  created: function () {
    this.recipeIndex();
  },
  methods: {
    recipeIndex: function () {
      console.log("recipes indexxxx");
      var params = {
        search: this.search,
        category: this.category,
      };
      console.log(this.$route.query.category);
      axios
        .get(
          "/api/recipes?search=" +
            this.$route.query.search +
            "&category=" +
            this.$route.query.category
        )
        .then((response) => {
          console.log(response.data);
          this.recipes = response.data;
        });
    },
  },
};
</script>