<template>
  <div>
    <b-container>
      <b-form @submit="addMovie">
        <b-row>
          <b-col sm="3"></b-col>
          <b-col sm="2">
            <label for="addMovieName">Name:</label>
          </b-col>
          <b-col sm="4">
            <b-form-input id="addMovieName" type="text" v-model="form.MovieName"></b-form-input>
          </b-col>
          <b-col sm="3"></b-col>
        </b-row>
        <b-row>
          <b-col sm="3"></b-col>
          <b-col sm="2">
            <label for="addMovieYear">Year:</label>
          </b-col>
          <b-col sm="4">
            <b-form-input id="addMovieYear" type="text" v-model="form.MovieYear"></b-form-input>
          </b-col>
          <b-col sm="3"></b-col>
        </b-row>
        <b-row>
          <b-col>
            <b-button type="submit">Add</b-button>
          </b-col>
        </b-row>
      </b-form>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "AddMovieForm",
  props: ["movie"],
  data() {
    return {
      form: {}
    };
  },
  methods: {
    addMovie(evt) {
      evt.preventDefault();
      if (this.form.MovieName != "" || this.form.MovieYear != "") {
        const newMovie = JSON.parse(JSON.stringify(this.form));
        this.$emit("addMovie", newMovie);
        this.form.MovieName = "";
        this.form.MovieYear = "";
      }
    }
  }
};
</script>
    
<style scoped>
label {
  font-size: 1.5rem;
}
</style>
