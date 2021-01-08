<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <router-link v-bind:to="{path: `/recipes?search=category&category=Vodka`}">
      <!-- <img src="@/assets/vodka.jpg" contain/> -->
      <h1>Vodka</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Gin`}">
      <!-- <img src="@/assets/vodka.jpg" contain/> -->
      <h1>Gin</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Whiskey`}">
      <!-- <img src="@/assets/whiskey.jpg"/> -->
      <h1>Whiskey</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Rum`}">
      <!-- <img src="@/assets/rum.jpg"/> -->
      <h1>Rum</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Tequila`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h1>Tequila</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Brandy`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h1>Brandy</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Liqueur`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h1>Liqueur</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Liquor`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h1>Schnapps</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Beer`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h1>Beer</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Wine`}">
      <!-- <img src="@/assets/vodka.jpg"/> -->
      <h1>Wine</h1>
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