<script>
import MainHero from "./MainHero.vue"

export default {
    data() {
        return {

        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/hero/${imgName}`, import.meta.url).href;
        }
    },
    components: {MainHero},
}
</script>

<template>
<main>
    <MainHero/>
</main>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

</style>
