<template>
  <div class="home">
    <h1>{{ message }}</h1>
    <router-link v-bind:to="{path: `/recipes?search=category&category=Vodka`}">
    <h1>Vodka</h1>
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