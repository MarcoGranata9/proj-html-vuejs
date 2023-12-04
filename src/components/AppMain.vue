<script>
import CoachingSection from "./CoachingSection.vue";
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
    components: { MainHero, CoachingSection },
}
</script>

<template>
<main>
    <MainHero/>
    <CoachingSection/>
</main>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

</style>
