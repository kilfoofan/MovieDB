<template>
  <div>
    <!--SeachForm-->
    <b-container v-if="sShow">
      <b-form @submit="SearchMovie">
        <b-row>
          <b-col sm="3"></b-col>
          <b-col sm="2">
            <label for="addMovieName">Name:</label>
          </b-col>
          <b-col sm="4">
            <b-form-input id="addMovieName" type="text" v-model="form.name"></b-form-input>
          </b-col>
          <b-col sm="3"></b-col>
        </b-row>
        <b-row>
          <b-col sm="3"></b-col>
          <b-col sm="2">
            <label for="addMovieYear">Year:</label>
          </b-col>
          <b-col sm="4">
            <b-form-input id="addMovieYear" type="text" v-model="form.year"></b-form-input>
          </b-col>
          <b-col sm="3"></b-col>
        </b-row>
        <b-row>
          <b-col>
            <b-button type="submit">Search</b-button>
          </b-col>
        </b-row>
      </b-form>
    </b-container>
    <!--Display-->
    <b-container v-if="dShow">
      <b-row>
        <b-col sm="3"></b-col>
        <b-col sm="7">
          <b-table dark hover :items="items"></b-table>
        </b-col>
      </b-row>
      <b-row>
        <b-col sm="4"></b-col>
        <b-col sm="4">
          <b-button @click="goBack">Back</b-button>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  name: "SearchMovieForm",
  props: ["movie"],
  data() {
    return {
      form: {
        name: "",
        year: ""
      },
      sShow: true,
      dShow: false,
      found: false,
      items: []
    };
  },
  methods: {
    SearchMovie(evt) {
      evt.preventDefault();
      const Movie = JSON.parse(JSON.stringify(this.form));
      this.movie.map(movie => {
        if (this.form.name == "" && this.form.year == "") {
          this.items.push({ name: movie.name, year: movie.year });
          this.sShow = false;
          this.dShow = true;
          this.found = true;
        }
        if (this.form.name != "") {
          if (movie.name.toLowerCase().includes(Movie.name.toLowerCase())) {
            this.items.push({ name: movie.name, year: movie.year });
            this.sShow = false;
            this.dShow = true;
            this.found = true;
          }
        }
        if (this.form.year != "") {
          if (movie.year.includes(Movie.year)) {
            this.items.push({ name: movie.name, year: movie.year });
            this.sShow = false;
            this.dShow = true;
            this.found = true;
          }
        }
      });

      if (this.found == false) {
        alert("Not Found");
      }
      if (this.found) {
        this.form.name = "";
        this.form.year = "";
      }
      this.found = false;
    },
    goBack(evt) {
      evt.preventDefault();
      this.items = [];
      this.dShow = false;
      this.sShow = true;
    }
  }
};
</script>
    
<style scoped>
label {
  font-size: 1.5rem;
}
</style>
