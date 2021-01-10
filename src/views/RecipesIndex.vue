<template>
  <div class="recipes-index">
    <!-- Main -->
    <div id="main">

      <!-- Featured Post -->
      <article class="post featured">
        <header class="major">
          <h2><a>{{this.$route.query.category}}</a></h2>
          <p>There are {{ recipes.length }} recipes to choose from!</p>
        </header>
      </article>

      <!-- Posts -->
      <section class="posts">
        <article v-for="recipe in recipes">
          <header>
            <h2><a v-bind:href="'/recipes/' + recipe.recipe_id">{{ recipe.name }}</a></h2>
          </header>
          <a v-bind:href="'/recipes/' + recipe.recipe_id"><p>{{ recipe.instructions }}</p></a>
          <!-- <ul class="actions special">
            <li><a href="#" class="button">Full Story</a></li>
          </ul> -->
        </article>
        
      </section>

      <!-- Footer -->
      <footer>
      </footer>

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
      message: "Look at all these awesome recipes!",
      recipes: [],
      name: "",
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
      console.log(this.$route.query);
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