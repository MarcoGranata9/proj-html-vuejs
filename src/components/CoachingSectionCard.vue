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
            return new URL(`../assets/img/coaching/${imgName}`, import.meta.url).href;
        }

    }
}
</script>

<template>
    <div class="card">
        <img :src="getImgPath(card.img)" alt="">
        <h4>{{card.title}}</h4>
        <p>{{ card.text }}</p>
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

.card {
    line-height: 2rem;
}

</style>