<template>
    <div class="content_wrapper">
        <div class="content">
            <h1>Contact</h1>
            <div class="description">
                <p class="pad-below">I can be reached via a number of ways:</p>
                <p>Email: <a href="mailto:Lily@lollyde.online">Lily@lollyde.online</a></p>
                <p>Twitter: <a href="https://twitter.com/lollyde_">lollyde_</a></p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Contact',
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