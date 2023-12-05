<script>
import CallToActionSection from "./CallToActionSection.vue";
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
    components: { MainHero, CoachingSection, CallToActionSection },
}
</script>

<template>
<main>
    <MainHero/>
    <CoachingSection/>
    <CallToActionSection/>
</main>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

</style>
