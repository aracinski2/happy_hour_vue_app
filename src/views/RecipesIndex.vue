<template>
  <div class="recipes-index">
    <h1>{{ message }}</h1>
    <div v-for="recipe in recipes">
      
      <h3>{{ recipe.name }}</h3>
      <h5>{{ recipe.alcoholic }}</h5>
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
      // search: "",
      // category: "",
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