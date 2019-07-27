<template>
    <li class="header__nav-links-element"><a v-bind:href="href"><img v-bind:src="img" v-bind:alt="alt"></a></li>
</template>

<script>
export default {
    name: "HeaderLinkExternal",
    props: ["href", "alt", "img"]
}
</script>

<style>

</style>
