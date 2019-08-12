<template>
  <div class="content_wrapper">
    <div class="content">
      <h1>{{header}}</h1>
      <div class="description">
        <p v-for="line in content" v-bind:key="line" v-html="line"></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Content",
  components: {},
  props: ["header", "content"]
};
</script>

<style>
p{
  pointer-events: all;
}
.content_wrapper {
  left: 50%;
  position: absolute;
  pointer-events: none;
  width: 50%;
  margin-top: 72px;
}
.content {
  background-color: rgba(0, 0, 0, 0);
  z-index: 10;
  text-align: center;
  padding: 5px;
  position: relative;
  left: -50%;
  display: flex;
  flex-direction: column;
}
h1 {
  color: #00b2d4;
  margin-top: 150px;
  text-transform: capitalize;
  font-size: 400%;
  align-self: center;
  pointer-events: all;
}
.description {
  font-size: 120%;
  color: lightgray;
}
</style>