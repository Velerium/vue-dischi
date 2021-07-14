<template>
    <div class="card">
        <div class="card-info">
            <img :src="poster" :alt="`image of ${title}`">
            <div class="card-more-info">
                <div class="card-title">
                    <h2>{{ title.toUpperCase() }}</h2>  <!-- Nice try. -->
                </div>
                <div class="card-other-info">
                    <div>{{ author }}</div>
                    <div>{{ year }}</div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        poster: String,
        title: String,
        author: String,
        year: String,
    }
}
</script>

<style lang="scss" scoped>

@import '../style/colors';
@import '../style/fonts';

    .card {
        width: 20%;
        padding: 10px 15px;
        font-family: $main-font;
        
        .card-info {
            background-color: $nav-bg;
            height: 100%;
            text-align: center;
            padding: 15px;
            display: flex;
            flex-direction: column;
        
            img {
                width: 100%;
                height: 50%;
                margin-bottom: 20px;
            }

            .card-more-info {

                .card-title {
                    height: 85px;
                    margin-bottom: 15px;

                    h2 {
                        font-size: 20px;
                        color: $h2-color;
                    }
                }

                .card-other-info {
                    
                    div {
                        font-size: 18px;
                        color: $span-color;
                    }
                }
            }
        }
    }

</style>