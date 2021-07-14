<template>
    <div class="loading-screen">
        <div class="loader">
            <font-awesome-icon class="loading-icon fa-spin" icon="spinner" />
            <div class="text">Caricamento in corso!</div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Loader',
}
</script>

<style lang="scss" scoped>

    @import '../style/fonts';
    @import '../style/colors';

    .loading-screen {
        height: 100vh;
        position: relative;
        background-color: $main-bg;

        .loader {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 40px;
            text-align: center;
            color: $h2-color;

            .text {
                font-size: 25px;
                font-family: $main-font;
                margin-top: 15px;
            }
        }
    }
</style>