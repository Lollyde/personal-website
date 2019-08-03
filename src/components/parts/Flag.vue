<template>
  <div id="particle_container">
  </div>
</template>

<script>
export default {
  name: 'Flag',
  components: {
  },
  mounted(){
      particlesJS.load('particle_container', '/particles-config.json');
  }
}
</script>

<style>
    #particle_container {
        z-index: -100;
        position: fixed;
        height: calc(100% - 72px);
        width: 100%;
        margin-top: 72px;
    }
</style>
