<template>
    <div class="content_wrapper">
        <div class="content">
            <h1>Portfolio</h1>
            <div class="description">
                <p>Most of my projects can be found on <a href="https://github.com/lollyde">github</a>.</p>
                <p>I will be adding more as I finish projects.</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Portfolio',
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