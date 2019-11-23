<template>
  <li
    class="header__nav-links-element"
    v-bind:class="{ header_active: active }"
    @click="$emit('load-link', text)"
  >
    <router-link
      @click="$emit('load-link', text)"
      v-bind:to="to"
      class="header__nav-links-element-text"
    >{{text}}</router-link>
  </li>
</template>

<script>
export default {
  name: "HeaderLink",
  props: ["to", "text", "active"],
  methods: {}
};
</script>
<style>
.header__nav-links-element-text {
  padding-top: 20px !important;
  padding-bottom: 29px !important;
  height: 20% !important;
  text-transform: capitalize;
  text-decoration: none;
  color: white;
  font-size: 120%;
}
</style>