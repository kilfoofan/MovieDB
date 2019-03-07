<template>
  <b-container fluid>
    <div id="app">
      <div id="nav">
        <router-link to="/">
          <b-button class="mr-2 my-3" variant="primary">Home</b-button>
        </router-link>
        <router-link to="/add">
          <b-button class="mr-2 my-3" variant="primary">Add Movie</b-button>
        </router-link>
        <router-link to="/search">
          <b-button class="mr-2 my-3" variant="primary">Search Movie</b-button>
        </router-link>
        <router-link to="/help">
          <b-button class="mr-2 my-3" variant="primary">Help</b-button>
        </router-link>
        <router-link to="/about">
          <b-button class="mr-2 my-3" variant="primary">About</b-button>
        </router-link>
      </div>
      <router-view v-bind:movie="movie" v-on:addMovie="addMovie"/>
    </div>
  </b-container>
</template>
<script>
export default {
  name: "Main",
  data() {
    return {
      movie: [
        { name: "Night of the Living Dead", year: "1968" },
        { name: "Plan 9 From Outerspace", year: "1959" }
      ]
    };
  },
  methods: {
    getName: function() {
      console.log(this.$refs.MovieName.value);
    },
    addMovie: function(newMovie) {
      //console.log(newMovie.MovieName);
      this.movie.push({ name: newMovie.MovieName, year: newMovie.MovieYear });
    }
  }
};
</script>


<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  height: 100%;
  text-align: center;
  text-shadow: 1px 1px #ffffff;
  color: #2c3e50;
  position: relative;
}
#app::after {
  content: "";
  background-image: url(./assets/bgimage.png);
  opacity: 0.2;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-size: 100%;
  min-height: 100vh;
  position: absolute;
  z-index: -1;
}
</style>
