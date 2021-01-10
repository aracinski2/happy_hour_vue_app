<template>
  <div class="recipes-search">
    <!-- Footer -->
    <footer id="footer">
      <section>
          <div>
            <div>
              <label>Search by a specific recipe name</label>
              <p><input type="text" v-model="name"></p>
              <button v-on:click="searchName()">Search</button>
            </div>
          </div>
      </section>
      <section class="split contact">
        <section class="alt">
          <div>
            <div>
              <label>Search by ingredients!</label>
              <p><input type="text" v-model="ingredient1"></p>
              <p><input type="text" v-model="ingredient2"></p>
              <p><input type="text" v-model="ingredient3"></p>
              <button v-on:click="searchIngredient()">Search</button>
            </div>
          </div>
        </section>
      </section>
    </footer>
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
    <!-- <h1>{{ message }}</h1>

    <h3>Search by a specific recipe name:</h3>
    <p><input type="text" v-model="name"></p> -->
    <!-- <router-link v-bind:to="{path: `/recipes?search=name&category=${this.name}`}">
    <h1>Search</h1>
    </router-link> -->
    <!-- <button v-on:click="searchName()">Search</button>

    <h1>OR</h1>

    <h3>Search by specific ingredients:</h3>
    <p><input type="text" v-model="ingredient1"></p>
    <p><input type="text" v-model="ingredient2"></p>
    <p><input type="text" v-model="ingredient3"></p>
    <button v-on:click="searchIngredient()">Search</button>

    <div v-for="recipe in recipes">
      <router-link v-bind:to="`/recipes/${recipe.recipe_id}`">
      <h3>{{ recipe.name }}</h3>
      </router-link>
      <br>
      <h5>{{ recipe.alcoholic }}</h5>
    </div> -->
  </div>
</template>

<style>
</style>

<script>
import axios from "axios";

export default {
  data: function () {
    return {
      message: "Do we have what your looking for?",
      recipes: [],
      name: "",
      ingredient1: "",
      ingredient2: "",
      ingredient3: "",
    };
  },
  created: function () {},
  methods: {
    searchName: function () {
      console.log("recipes searchhhhh");
      // console.log(this.$route.query);
      axios
        .get("/api/recipes?search=name&name=" + this.name)
        .then((response) => {
          console.log(response.data);
          this.recipes = response.data;
        });
    },
    searchIngredient: function () {
      console.log("recipes searchhhhh");
      // console.log(this.$route.query);
      axios
        .get(
          "/api/recipes?search=ingredient&ingredient1=" +
            this.ingredient1 +
            "&ingredient2=" +
            this.ingredient2 +
            "&ingredient3=" +
            this.ingredient3
        )
        .then((response) => {
          console.log(response.data);
          this.recipes = response.data;
        });
    },
  },
};
</script>
