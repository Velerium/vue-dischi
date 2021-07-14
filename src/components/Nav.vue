<template>
    <div class="nav">
        <img src="../assets/spotify-logo.png" alt="">
    </div>
</template>

<script>
export default {
    name: 'Nav',
}
</script>

<style lang="scss" scoped>

@import '../style/colors';

    .nav {
        height: 60px;
        background-color: $nav-bg;
        display: flex;
        align-items: center;

        img {
            width: 50px;
            margin-left: 10px;
        }
    }

</style>