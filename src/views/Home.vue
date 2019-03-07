<template>
  <div class="home">
    <b-row>
      <b-col sm="3"></b-col>
      <b-col sm="5">
        <h2>Welcome to using Movie Collection</h2>
      </b-col>
    </b-row>
    <b-row>
      <b-col sm="3"></b-col>
      <b-col sm="5">
        <p
          class="hello"
        >Movie Collection is an app for storing and finding movies in your own collection.</p>
      </b-col>
    </b-row>
    <b-row>
      <b-col sm="3"></b-col>
      <b-col sm="5">
        <p class="hello">For info on how to use this application, please refer to
          <router-link to="/help">
            <img src="../assets/Torchlight_help_icon.svg" height="24" width="24">
          </router-link>.
        </p>
      </b-col>
    </b-row>
    <b-row>
      <b-col sm="3"></b-col>
      <b-col sm="5">
        <p class="hello">For more information about movies please click on the movie posters below.</p>
      </b-col>
    </b-row>

    <a href="http://www.imdb.com">
      <img class="kuva1" src="../assets/500px-Plan_9_Alternative_poster.jpg" alt="Image 1">
      
      <img class="kuva2" src="../assets/livingdead.jpg" alt="Image 2">
    </a>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "home"
};
</script>

<style scoped>
.hello {
  text-align: justify;
}
.kuva1 {
  width: 20%;
  margin-left: 20%;
  margin-right: 20%;
}
.kuva2 {
  width: 60%;
  margin-left: 20%;
  margin-right: 20%;
}
</style>
