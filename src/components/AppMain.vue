<script>
import CallToActionSection from "./CallToActionSection.vue";
import CoachingSection from "./CoachingSection.vue";
import MainHero from "./MainHero.vue"
import VideoSection from "./VideoSection.vue";

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
    components: { MainHero, CoachingSection, CallToActionSection, VideoSection },
}
</script>

<template>
<main>
    <MainHero/>
    <CoachingSection/>
    <CallToActionSection/>
    <VideoSection/>
</main>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

</style>
