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