<script>
import CoursesCard from './CoursesCard.vue';

export default {
    data() {
        return {
            cardsArray: [
                {
                    img: "artist-course-08-480x480.jpg",
                    pirce: "$18.00",
                    title: "The Acrilic Painting Academy",
                    lessons: "4 Lessons",
                    students: "50 Students",
                },
                {
                    img: "artist-course-07-480x480.jpg",
                    pirce: "$21.00",
                    title: "Drawing and Shading: Complete Course",
                    lessons: "14 Lessons",
                    students: "50 Students",
                },
                {
                    img: "artist-course-06-480x480.jpg",
                    pirce: "$19.00",
                    title: "The Color Theory for Digital Artist",
                    lessons: "7 Lessons",
                    students: "50 Students",
                },
                {
                    img: "artist-course-05-480x480.jpg",
                    pirce: "$35.00",
                    title: "Ultimate Guide to Digital Sketching for Beginner",
                    lessons: "14 Lessons",
                    students: "50 Students",
                },
                {
                    img: "artist-course-04-480x480.jpg",
                    pirce: "$19.00",
                    title: "Portrait Drawing The Smart Way",
                    lessons: "2 Lessons",
                    students: "50 Students",
                },
                {
                    img: "artist-course-03-480x480.jpg",
                    pirce: "$19.00",
                    title: "Mastering Watercolor Painting from Beginner",
                    lessons: "9 Lessons",
                    students: "50 Students",
                },
                {
                    img: "artist-course-02-480x480.jpg",
                    pirce: "$25.00",
                    title: "The Art & Science of Drawing",
                    lessons: "4 Lessons",
                    students: "50 Students",
                },
                {
                    img: "artist-course-01-480x480.jpg",
                    pirce: "$22.00",
                    title: "The Colored Pencil Drawing Course",
                    lessons: "6 Lessons",
                    students: "50 Students",
                },
            ],
            bgImg: "artist-shape-01-600x577.png",
        };
    },
    components: { CoursesCard },
    methods:{
        getImgPath(imgName) {
            return new URL(`../assets/img/${imgName}`, import.meta.url).href;
        }

    }
}
</script>

<template>
    <section>
        <div class="container">
            <div class="title">
                <h2>Artist Coaching</h2>
                <h3>Latest Online Coureses</h3>
            </div>
            <div class="row">
                <div class="col" v-for="card in cardsArray">
                    <CoursesCard :card="card"/>
                </div>
            </div>        
        </div>
        <div class="btn-container">
            <button class="btn-light">View all courses <i class="fa-solid fa-arrow-right"></i></button>
        </div>
        <img :src="getImgPath(bgImg)" class="bg-r" alt="">
        <img :src="getImgPath(bgImg)" class="bg-l" alt="">
    </section>
</template>

<style scoped lang="scss">         
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

section {
    padding: 4rem 0;
    position: relative;
    z-index: 1;
    overflow: hidden;
    .title {
        text-align: center;
        h2 {
        font-family: 'Dancing Script Variable', sans-serif;
        color: $title-color;
        font-size: 3rem
        }
        h3{
            font-size: 1.6rem;
        }
    }
    .row {
        @include flex(space-between, start, row);
        flex-wrap: wrap;
        position: relative;
        z-index: 1;

        .col {
            width: calc(100% / 4);
        }
    }
    .btn-container{
        @include flex(center, center, row);
        padding: 2rem;
        .btn-light{
            padding: 1rem 2rem
        }
    }
    .bg-r{
        position: absolute;
        z-index: 0;
        top: 10%;
        right: -20%;
        transform: rotate(270deg);
    }
    .bg-l{
        position: absolute;
        z-index: 0;
        bottom: 20%;
        left: -20%;
    }
}
</style>