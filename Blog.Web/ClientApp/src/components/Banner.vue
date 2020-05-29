<template>
    <div class="banner"/>
</template>
<script>
    export default {
        name: 'blog-banner'
    }
</script>
<style>
    .banner {
        background: url("../assets/banner-01.jpg") center 0 / cover no-repeat fixed;
        display: table;
        text-align: center;
        position: relative;
        min-height: 1000px;
        width: 100%;
        height: 100%;
    }

    .banner::after {
        content: " ";
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: #000;
        z-index: 0;
        opacity: .6;
    }
</style>