<template>
    <div class="content">
        <div class="container">
            <Card v-for="(record, index) in records" :key="index"
                :poster="record.poster"
                :title="record.title"
                :author="record.author"
                :year="record.year"
            />
        </div>
    </div>
</template>

<script>
import Card from './Card.vue'
export default {
    name: 'Main',
    components: {
        Card
    },
    props: {
        records: Array,
    }
}
</script>

<style lang="scss" scoped>

@import '../style/colors';

.content {
    background-color: $main-bg;
    display: flex;
    flex-grow: 1;

    .container {
        margin: 70px auto;
        width: 1100px;
        display: flex;
        flex-wrap: wrap;
    }
}

</style>