<template>
  <div id="app">
    <Header />
    <Flag />
    <router-view />
  </div>
</template>

<script>
import Header from "./components/parts/Header";
import Flag from "./components/parts/Flag";
import Content from "./components/parts/Content";
import VueRouter from "vue-router";

const component_data = {
  home_data: {
    header: `Hello.`,
    content: [
      `I'm Lily. I'm a developer currently living in germany.`,
      `I mainly focus on desktop applications, though I'm learning webdev and am willing to learn pretty much anything.`,
      `I am also an avid Twitch viewer and moderator.`,
      `Welcome to my site!`
    ]
  },
  portfolio_data: {
    header: `Portfolio`,
    content: [
      `Most of my projects can be found on <a href="https://github.com/lollyde">github</a>.`,
      `I will be adding more as I finish projects.`
    ]
  },
  contact_data: {
    header: `Contact`,
    content: [
      `I can be reached via a number of ways:`,
      `Email: <a href="mailto:Lily@lollyde.online">Lily@lollyde.online</a>`,
      `Twitter: <a href="https://twitter.com/lollyde_">lollyde_</a>`
    ]
  },
  about_data: {
    header: `About`,
    content: [
      `This site was built using <a href="https://vuejs.org/">Vue.js</a>`,
      `Icons made by <a href="https://3v.fi">3v</a>`,
      `Background made using a slightly modified version of <a href="https://vincentgarreau.com/particles.js/">particles.js</a>`,
      `This website is hosted on my own server with <a href="https://nginx.org/">Nginx</a>`
    ]
  },
  notfound_data: {
    header: `404`,
    content: [`Requested page wasnt found :(`]
  }
};

const router = new VueRouter({
  mode: "history",
  base: __dirname,
  routes: [
    {
      path: "/",
      component: Content,
      props: () => ({
        content: component_data.home_data.content,
        header: component_data.home_data.header
      })
    },
    {
      path: "/portfolio",
      component: Content,
      props: () => ({
        content: component_data.portfolio_data.content,
        header: component_data.portfolio_data.header
      })
    },
    {
      path: "/contact",
      component: Content,
      props: () => ({
        content: component_data.contact_data.content,
        header: component_data.contact_data.header
      })
    },
    {
      path: "/about",
      component: Content,
      props: () => ({
        content: component_data.about_data.content,
        header: component_data.about_data.header
      })
    },
    {
      path: "*",
      component: Content,
      props: () => ({
        content: component_data.notfound_data.content,
        header: component_data.notfound_data.header
      })
    }
  ]
});

export default {
  router,
  name: "app",
  components: {
    Header,
    Flag
  }
};
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
  color: #00b2d4;
  margin-top: 150px;
  text-transform: capitalize;
  font-size: 400%;
}

table,
th,
td {
  border: 1px solid rgba(0, 187, 212, 0.8);
  border-collapse: collapse;
}
</style>
