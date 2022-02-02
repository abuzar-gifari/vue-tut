<template>


  <router-link to="/">Home Page</router-link>
  <br>
  <router-link to="/login">Login Page</router-link>
  <br>
  <router-link to="/profile/peter">Peter's Profile Page</router-link>
  <br>
  <router-link to="/profile/anil">Anil's Profile</router-link>
  <br>
  <router-link to="/profile/sidhu">Sidhu's Profile</router-link>
  <br>
  <router-view />


</template>

<script>

export default {
  name: 'App'
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
