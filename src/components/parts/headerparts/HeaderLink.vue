<template>
    <li class="header__nav-links-element" v-bind:class="{ header_active: active }" @click="$emit('load-link', text)"><router-link @click="$emit('load-link', text)" v-bind:to="to" class="header__nav-links-element-text">{{text}}</router-link></li>
</template>

<script>
export default {
    name: "HeaderLink",
    props: ["to", "text", "active"],
    methods: {
    }
}
</script>
<style>

</style>
