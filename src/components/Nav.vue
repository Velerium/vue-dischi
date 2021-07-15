<template>
    <div class="nav">
        <img src="../assets/spotify-logo.png" alt="">
        <form action="">
        
        <label for="genres">Pick a genre!</label>

        <select v-model="selectedOption" @change="$emit('filter', selectedOption)" name="genres" id="genres">
            <option value="All">All</option>
            <option v-for="option in genres" :key="option" :value=option >{{ option }}</option>
        </select>

        </form>
    </div>
</template>

<script>
export default {
    name: 'Nav',
    data () {
        return  {
            selectedOption: 'All',
        }       
    },
    props: {
        genres: Array,
    },
}

</script>

<style lang="scss" scoped>

@import '../style/colors';
@import '../style/fonts';

    .nav {
        height: 60px;
        padding: 0 30px;
        background-color: $nav-bg;
        display: flex;
        justify-content: space-between;
        align-items: center;

        label {
            color: $h2-color;
            margin-right: 10px;
        }

        img {
            width: 50px;
            margin-left: 10px;
        }
    }

</style>