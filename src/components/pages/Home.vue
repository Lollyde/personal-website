<template>
    <div class="content_wrapper">
        <div class="content">
            <h1> Hello. </h1>
            <div class="description">
                <p>I'm Lily. I'm a developer currently living in germany.</p>
                <p>I mainly focus on desktop applications, though I'm learning webdev and am willing to learn pretty much anything.</p>
                <p>I am also an avid Twitch viewer and moderator.</p>
                <p>Welcome to my site!</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Home',
  components: {
  }
}
</script>

<style>
    .content_wrapper {
        left: 50%;
        position: absolute;
        pointer-events: none;
        width: 50%;
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
