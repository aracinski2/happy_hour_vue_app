<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <h2>Click on a category of alcohol to get it's recipes</h2>
    <router-link v-bind:to="{path: `/recipes?search=category&category=Vodka`}">
      <!-- <img src="@/assets/vodka.jpg" contain/> -->
      <h2>Vodka</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Gin`}">
      <!-- <img src="@/assets/vodka.jpg" contain/> -->
      <h2>Gin</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Whiskey`}">
      <!-- <img src="@/assets/whiskey.jpg"/> -->
      <h2>Whiskey</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Rum`}">
      <!-- <img src="@/assets/rum.jpg"/> -->
      <h2>Rum</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Tequila`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h2>Tequila</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Brandy`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h2>Brandy</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Liqueur`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h2>Liqueur</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Liquor`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h2>Schnapps</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Beer`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h2>Beer</h2>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Wine`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h2>Wine</h2>
    </router-link>
    
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function () {
    return {
      message: "Happy Hour",
    };
  },
  created: function () {},
  methods: {},
};
</script>