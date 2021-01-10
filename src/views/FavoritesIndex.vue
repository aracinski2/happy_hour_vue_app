<template>
  <div class="favorites-index">
    <!-- Navbar -->
    <nav id="nav">
      <ul class="links">
        <li><a href="/">Home</a></li>
        <li><a href="/search">Search</a></li>
        <li class="active"><a href="/favorites">Favorites
        </a></li>
        <li><a href="/login">Login</a></li>
        <li><a href="/logout">Logout</a></li>
        <li><a href="/signup">Signup</a></li>
      </ul>
      <ul class="icons">
        <!-- <li><a href="#" class="icon brands fa-facebook-f"><span class="label">Facebook</span></a></li> -->
        <li><a href="https://www.linkedin.com/in/alexander-racinski/" class="icon brands fa-linkedin"><span class="label">LinkedIn</span></a></li>
        <li><a href="https://github.com/aracinski2" class="icon brands fa-github"><span class="label">GitHub</span></a></li>
      </ul>
    </nav>
    <div id="main">

      <!-- Featured Post -->
      <article class="post featured">
        <header class="major">
          <h2><a>Favorites</a></h2>
        </header>
      </article>

      <!-- Posts -->
      <section class="posts">
        <article v-for="favorite in favorites">
          <header>
            <h2><a v-bind:href="'/recipes/' + favorite.recipe_id">{{ favorite.recipe.name }}</a></h2>
          </header>
          <a v-bind:href="'/recipes/' + favorite.recipe_id"><p>{{ favorite.recipe.instructions }}</p></a>
          <button v-on:click="favoritesDestroy(favorite)">Remove</button>
          <!-- <ul class="actions special">
            <li><a href="#" class="button">Full Story</a></li>
          </ul> -->
        </article>
      </section>
    </div>
    <!-- <h1>{{ message }}</h1>
    <div v-for="favorite in favorites">
      <router-link v-bind:to="`/recipes/${favorite.recipe_id}`">
        <h3> {{ favorite.recipe.name }} </h3>
        <h5> {{ favorite.recipe.alcoholic }} </h5>
      </router-link>
        <button v-on:click="favoritesDestroy()">Remove</button> -->
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
      // favorite: [],
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
    favoritesDestroy: function (favorite) {
      axios.delete("/api/favorites/" + favorite.id).then((response) => {
        console.log("favorite destroy", response);
        var index = this.favorites.indexOf(favorite);
        this.favorites.splice(index, 1);
      });
    },
  },
};
</script>
