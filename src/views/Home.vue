<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <router-link v-bind:to="{path: `/recipes?search=category&category=Vodka`}">
    <h1>Vodka</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Whiskey`}">
    <h1>Whiskey</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Rum`}">
    <h1>Rum</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Liquor`}">
    <h1>Liqueur</h1>
    </router-link>

    <router-link v-bind:to="{path: `/recipes?search=category&category=Wine`}">
    <h1>Wine</h1>
    </router-link>
    
    <router-link v-bind:to="{path: `/recipes?search=category&category=Tequila`}">
    <h1>Tequila</h1>
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