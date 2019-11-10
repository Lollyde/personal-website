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
      `<h2>Languages</h2>`,
      `Learning Java since 2014, actively developing for three years`,
      `Learning C# since 2016, actively developing since then`,
      `A bit of JS I picked up over the years`,
      `Rudimentary experience in Lisp (Scheme dialect), Python, Node.js, Bash`,
      `Currently also learning Go`,
      `<br>`,
      `<h2>Projects</h2>`,
      `Contributor to the <a href="https://github.com/EverestAPI/Everest">EverestAPI</a> modloader for Celeste`,
      `<a href="https://github.com/lollyde/CelesteRandomizer">Celeste Randomizer</a>, a mod for Celeste using the EverestAPI`,
      `A couple of simple Twitch chatbots implemented using <a href="https://github.com/TwitchLib/TwitchLib">TwitchLib</a>`,
      `<a href="https://github.com/lollyde/personal-website">This website</a>, using Vue.js`,
      `"Nine men's morris" AI written in Java (Uni project)`,
      `"Organization Helper" app for Android + backend developed in Java (Uni project)`,
      `Sadly I cannot provide the source code for my Uni projects.`,
      `Other projects can be found on <a href="https://github.com/lollyde">github</a>`,
      `I will be adding more as I finish projects`
    ]
  },
  contact_data: {
    header: `Contact`,
    content: [
      `I can be reached via a number of ways:`,
      `Email: <a href="mailto:Lily@lollyde.online">Lily@lollyde.online</a>`,
      `Twitter: <a href="https://twitter.com/lollyde_">lollyde_</a>`,
      `Discord: Lollyde#1337`
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
</style>
