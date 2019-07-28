<template>
  <div>
    <header class="header">
        <nav class="header_nav">
            <ul class="header_bars">
                <li id="left_header">
                    <ul class="header_nav-links">
                        <li v-for="link in HeaderLinks.Internal" v-bind:key="link.text">
                            <HeaderLink v-bind:to="link.to" v-bind:text="link.text" v-bind:active="link.active" v-on:load-link="linkClicked"/>
                        </li>
                    </ul>
                </li>
                <li id="right_header">
                    <ul class="header_nav-links">
                        <li v-for="link in HeaderLinks.External" v-bind:key="link.alt">
                            <HeaderLinkExternal v-bind:href="link.href" v-bind:alt="link.alt" v-bind:img="link.img"/>
                        </li>
                    </ul>
                </li>
            </ul>
        </nav>
    </header>
  </div>
</template>

<script>
import HeaderLink from "./HeaderLink";
import HeaderLinkExternal from "./HeaderLinkExternal";

export default {
  name: 'Header',
  components: {
      HeaderLink,
      HeaderLinkExternal
  },
  data() {
    return {
      HeaderLinks: {
        External: [
          {
            href: "https://github.com/lollyde",
            alt: "Github",
            img: "/svg/github.svg"
          },
          {
            href: "https://steamcommunity.com/id/lollyde3/",
            alt: "Steam",
            img: "/svg/steam.svg"
          },
          {
            href: "https://twitter.com/lollyde_",
            alt: "Twitter",
            img: "/svg/twitter.svg"
          },
          {
            href: "https://twitch.tv/lollyde",
            alt: "Twitch",
            img: "/svg/twitch.svg"
          }
        ],
        Internal: [
          {
            to: "/",
            text: "home",
            active: false
          },
          {
            to: "/portfolio",
            text: "portfolio",
            active: false
          },
          {
            to: "/contact",
            text: "contact",
            active: false
          },
          {
            to: "/about",
            text: "about",
            active: false
          }
        ]
      }
    }
  },
  methods: {
      linkClicked(text){
          this.HeaderLinks.Internal.forEach(element => {
              element.active = element.text === text;
          });
      }
  },
  beforeMount: function(){
    var tmp = this.$route.path.split('/')[1];
    if(tmp.length === 0){
      this.linkClicked("home");
    }else{
      this.linkClicked(tmp);
    }
  }
}
</script>

<style>
    .header_active {
        background-color: rgba(0, 187, 212, 0.5) !important;
    }

    .header {
        border-top: 5px solid rgba(0, 187, 212, 0.8);
        height: 67px;
        width: 100%;
        background-color: #3b3b3b;
        z-index: 20;
    }

    .header_nav {
        display: block;
        background-color: inherit;
        height: inherit;
    }

    .header_bars {
        margin: 0;
        padding: 0;
        list-style-type: none;
        background-color: inherit;
        height: inherit;
    }

    .header_bars li {
        background-color: inherit;
        list-style-type: none;
        display: inline-block;
        height: inherit;
    }


    .header_nav-links {
        list-style-type: none;
        margin: 0;
        padding: 0;
        overflow: hidden;
        width: 100%;
        background-color: inherit;
        height: inherit;
    }

    .header__nav-links-element {
        text-transform: capitalize;
        text-align: center;
        line-height: inherit;
        display: block;
        background-color: inherit;
        height: inherit;
    }

    .header__nav-links-element img {
        padding-top: 0;
        height: inherit;
        background-color: inherit;
        color: lightgrey;
    }


    .header__nav-links-element a {
        height: 35px;
        display: block;
        background-color: inherit;
        padding: 16px;
    }

    .header__nav-links-element:hover {
        background-color: #101010;
    }


    .header__nav-links-element-text {
        padding-top: 20px !important;
        padding-bottom: 29px !important;
        height: 20% !important;
        text-transform: capitalize;
        text-decoration: none;
        color: white;
        font-size: 120%;
    }
    #left_header {
        float: left;
    }

    #right_header {
        float: right;
    }
</style>
