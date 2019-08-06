<template>
    <div class="content_wrapper">
        <div class="content">
            <h1>About</h1>
            <div class="description">
                <p>This site was built using <a href="https://vuejs.org/">Vue.js</a></p>
                <p>Icons made by <a href="https://3v.fi">3v</a></p>
                <p>Background made using a slightly modified version of <a href="https://vincentgarreau.com/particles.js/">particles.js</a></p>
                <p>This website is hosted on my own server with Nginx.</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'About',
  components: {
  }
}
</script>

<style>
    .content_wrapper {
        left: 50%;
        position: absolute;
        pointer-events: none;
    }
    .content {
        background-color: rgba(0,0,0,0);
        z-index: 10;
        text-align: center;
        padding: 5px;
        position: relative;
        left: -50%;
    }
    .description {
        font-size: 120%;
        color: lightgray;
    }
</style>