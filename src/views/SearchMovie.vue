<template>
  <div>
    <SearchMovieForm v-bind:movie="movie"/>
  </div>
</template>

<script>
import SearchMovieForm from "../components/SearchMovieForm.vue";
export default {
  name: "SearchMovie",
  props: ["movie"],
  components: {
    SearchMovieForm
  }
};
</script>

<style scoped>
</style>
