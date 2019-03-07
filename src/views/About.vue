<template>
  <div class="about">
    <b-row>
      <b-col sm="3"></b-col>
      <b-col sm="6">
        <h2 class="notice">Notice:</h2>
        <p
          class="notice"
        >This version does not have any backend or API functionality. It is meant to be a frontend shell and shows simulated functionality.</p>
        <p>
          In the "database" there are two movies for testing purposes, "Plan 9 from outerspace" and "Night of the living dead". You are able to
          add movies to the "database", but the changes are not persistant.
        </p>
      </b-col>
      <b-col sm="3"></b-col>
    </b-row>
    <b-row>
      <b-col sm="3"></b-col>
      <b-col sm="6">
        <p>This application has been coded by Arto Vesterbacka.</p>
        <p>Contact via email at arto dot vesterbacka at gmail dot com</p>
      </b-col>
      <b-col sm="3"></b-col>
    </b-row>
  </div>
</template>
<style scoped>
.notice {
  color: red;
  text-align: justify;
}
p {
  text-align: justify;
}
</style>

