<template>
  <li class="header__nav-links-element">
    <a v-bind:href="href" v-bind:title="title">
      <img v-bind:src="img" />
    </a>
  </li>
</template>

<script>
export default {
  name: "HeaderLinkExternal",
  props: ["href", "title", "img"]
};
</script>
<style>
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
</style>