<script>
export default {
    data() {
        return {
            
        }
    },
    props: {
        card: Object
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/testimonials/${imgName}`, import.meta.url).href;
        }
    },
}
</script>

<template>
    <div class="card">

        <h4>{{ card.title }}</h4>
        <p>{{ card.text }}</p>

        <div class="info">
            <img :src="getImgPath(card.img)" alt="">
            <div class="info-text">
                <p class="bold">{{ card.name }}</p>
                <p>/{{ card.job }}</p> 
            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;
.card {
    background-color: white;
    padding: 2rem;
    border-radius: 10px;

    h4 {
        margin-bottom: 2rem;
        line-height: 1.5rem;
    }
    p{
        margin-bottom: 2rem;
        line-height: 1.5rem;
    }
    .info {
        @include flex(start, center, row);
        img {
            border-radius: 50%;
            width: 80px;
        }
        .info-text {
            p {
                margin-bottom: 0;
                margin-left: 20px;
            }
            .bold {
                font-weight: bold;
            }
        }
    }
}
</style>