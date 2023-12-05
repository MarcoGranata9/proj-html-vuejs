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
            return new URL(`../assets/img/course/${imgName}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <div class="card">
        <img :src="getImgPath(card.img)" alt="">
        <div class="text">
            <p>{{ card.pirce }}</p>
            <h4>{{ card.title }}</h4>
            <div class="info">
                <span><i class="fa-regular fa-file-lines"></i> {{ card.lessons }}</span>
                <span><i class="fa-regular fa-user"></i> {{ card.students }}</span>
            </div> 
        </div>
       
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

.card {
    padding: 0.5rem;
    img {
        width: 350px;
    }
    .text {
        padding: 1.5rem;
        padding-right: 2rem;
        p {
            color: $btn-bg;
            font-weight: bold;
            margin-bottom: 1rem;
        }
        h4 {
            line-height: 1.5rem;
            font-size: 1.2rem;
            margin-bottom: 1rem;
        }
    }

    .info {
        display: flex;
        justify-content: space-between;
        color: gray;
    }
}
</style>