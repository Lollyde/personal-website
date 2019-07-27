<template>
  <div id="app">
    <Header />
    <Flag />
    <router-view />
  </div>
</template>

<script>
import Header from "./components/Header";
import Flag from "./components/Flag";
import Home from "./components/Home"
import Portfolio from "./components/Portfolio"
import Contact from "./components/Contact"
import About from "./components/About"
import VueRouter from 'vue-router';

const router = new VueRouter({
  mode: 'history',
  base: __dirname,
  routes: [
    { path: '/', component: Home },
    { path: '/portfolio', component: Portfolio },
    { path: '/contact', component: Contact },
    { path: '/about', component: About}
  ]
})


export default {
  router,
  name: 'app',
  components: {
    Header,
    Flag
  }
}
</script>

<style>
  html {
    background-color: #1e1e1e;
    color: lightgrey;
  }

  body {
    margin: 0;
  }

  a {
    text-decoration: none;
    color: #42a5f5;
    background: inherit;
    pointer-events: all;
  }

  h1 {
    color: #00B2D4;
    margin-top: 150px;
    text-transform: capitalize;
    font-size: 400%;
  }

  table, th, td {
    border: 1px solid rgba(0, 187, 212, 0.8);
    border-collapse: collapse;
  }
</style>
