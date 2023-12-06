<script>
export default {
    data() {
        return {
            
        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/events/${imgName}`, import.meta.url).href;
        }
    },
    props: {
        card: Object
    }
}
</script>

<template>
    <div :class="card.class" class="card">
        <img :src="getImgPath(card.img)" alt="">
        <div class="text">
            <p class="date">{{ card.date }}</p>
            <h4>{{ card.title }}</h4>
            <p><i class="fa-solid fa-location-dot"></i> {{ card.location }}</p>
        </div>
    </div>
</template>

<style scoped lang="scss"> 
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;
.card{
    @include flex(start, center, row);
    .text {
        padding: 0 2rem;
        width: 300px;
        p{
            color: gray;
        }
        .date{
            font-size: 1.1rem;
        }
        h4{
            font-size: 1.3rem;
        }
        & > * {
            margin-bottom: 2rem;
        }
    }
}
</style>