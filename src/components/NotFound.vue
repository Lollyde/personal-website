<template>
    <div class="content_wrapper">
        <div class="content">
            <h1> 404 </h1>
            <div class="description">
                <p>Requested page wasnt found :(</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'NotFound',
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
