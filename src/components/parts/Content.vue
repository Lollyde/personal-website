<template>
  <div class="content_wrapper">
    <div class="content">
      <simplebar class="bar" data-simplebar-auto-hide="false">
        <h1>{{header}}</h1>
        <div class="description">
          <p v-for="line in content" v-bind:key="line" v-html="line"></p>
        </div>
      </simplebar>
    </div>
  </div>
</template>

<script>
import simplebar from 'simplebar-vue';
import 'simplebar/dist/simplebar.min.css';

export default {
  name: "Content",
  components: {
    simplebar
  },
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
  width: 50%;
  margin-top: 72px;
  height: calc(100% - 72px);
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
  height: calc(100% - 10px);
  overflow: hidden;
}
h1 {
  color: #00b2d4;
  margin-top: 150px;
  text-transform: capitalize;
  font-size: 400%;
  align-self: center;
}
h2 {
  color: #00b2d4;
  text-transform: capitalize;
}
.description {
  font-size: 120%;
  color: lightgray;
}
.simplebar-track {
  background-color: rgba(0, 0, 0, 0.2);
}
.simplebar-scrollbar::before {
  background-image: linear-gradient(rgb(79, 165, 194) 0%, rgb(79, 165, 194) 20%, rgb(245, 135, 135) 20%, rgb(245, 135, 135) 40%, rgb(249, 251, 252) 40%, rgb(249, 251, 252) 60%, rgb(245, 135, 135) 60%, rgb(245, 135, 135) 80%, rgb(79, 165, 194) 80%, rgb(79, 165, 194) 100%);
}
.bar {
  height: inherit;
}
</style>