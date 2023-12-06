<script>
import BlogSection from "./BlogSection.vue";
import CallToActionSection from "./CallToActionSection.vue";
import CoachingSection from "./CoachingSection.vue";
import CoursesSection from "./CoursesSection.vue";
import EventsSection from "./EventsSection.vue";
import MainHero from "./MainHero.vue"
import Newsletter from "./Newsletter.vue";
import TestimonialsSection from "./TestimonialsSection.vue";
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
    components: { MainHero, CoachingSection, CallToActionSection, VideoSection, TestimonialsSection, CoursesSection, BlogSection, EventsSection, Newsletter },
}
</script>

<template>
<main>
    <MainHero/>
    <CoachingSection/>
    <CallToActionSection/>
    <VideoSection/>
    <TestimonialsSection/>
    <CoursesSection/>
    <BlogSection/>
    <EventsSection/>
    <Newsletter/>
</main>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

</style>
