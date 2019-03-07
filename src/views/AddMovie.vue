<template>
  <div>
    <AddMovieForm v-bind:movie="movie" v-on:addMovie="addMovie"/>
  </div>
</template>

<script>
import AddMovieForm from "../components/AddMovieForm.vue";
export default {
  name: "AddMovie",
  components: {
    AddMovieForm
  },
  methods: {
    addMovie: function(newMovie) {
      this.$emit("addMovie", newMovie);
    }
  },
  props: ["movie"]
};
</script>

<style scoped>
</style>
