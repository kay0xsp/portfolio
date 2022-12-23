<template>
  <div id="app">
    <navbar />
    <router-view/>
  </div>
</template>

<script>
import navbar from "./components/NavBar.vue";

export default {
  components: { navbar },
};
</script>

<style>
h1,h2,h3,h4,h5,li{
  margin:0;
  list-style-type: none;
}
a{text-decoration: none; color: #2c3e50;}

body{
  margin:0;
}

.v-breadcrumbs{
  padding:0 !important;
  margin-left:5em !important;
}

#app {
  font-family: 'arimo';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

nav a {
  margin: 0 5px;
  font-weight: bold;
  color: #2c3e50;
  transition:0.5s;
}

nav a:hover{
  color: #218fd8;
}

nav a.router-link-exact-active {
  color: #218fd8;
}

@font-face {
font-family:'arimo';
src: url('./assets/fonts/Arimo-Regular.ttf');
font-weight: normal;
font-style: normal;
}
</style>
