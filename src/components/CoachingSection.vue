<script>
import CoachingSectionCard from './CoachingSectionCard.vue';

export default {
    data() {
        return {
            cardArray: [
                {
                    img: "artist-box-image-01.png",
                    title: "Online Courses",
                    text: "Online art coaching now offers you a very powerful way to redesign your artist mind."
                },
                {
                    img: "artist-box-image-02.png",
                    title: "One to One",
                    text: "Getting the necessary clarity about the current state to help you improve your abilty."
                },
                {
                    img: "artist-box-image-03.png",
                    title: "Anywhere",
                    text: "Acces to valuable and portable program which allow you to set up and live anywhere you want."
                },
                {
                    img: "artist-box-image-04.png",
                    title: "On time",
                    text: "Punctuality is out top priority because it's an essential criteria to asses a program qualty."
                },

            ],
            bgArray: [
            {
                path: "maxcoach-shape-13.png",
                class: "maxcoach-shape-13"
            },
            {
                path: "artist-shape-01-600x577.png",
                class: "artist-shape-01"
            },
            ],
        };
    },
    components: { CoachingSectionCard },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/${imgName}`, import.meta.url).href;
        }
    }
}
</script>

<template>
<section class="coaching">
    <div class="container-m">
        <img :class="bgArray[0].class" :src="getImgPath(bgArray[0].path)" alt="">
        <img :class="bgArray[1].class" :src="getImgPath(bgArray[1].path)" alt="">
        <div class="wrapper">
            <div class="title">
                <h2>Artist coaching</h2>
                <h3>I understand what it takes to create.</h3>
                <h3>I can help you with:</h3>
            </div>
            <div class="row">
                <div class="col">
                    <CoachingSectionCard v-for="card in cardArray" :card="card"/>
                </div>
            </div>
        </div>
    </div>
</section>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

section {
    background-image: url(../assets/img/maxcoach-shape-14.png);
    text-align: center;
    margin: 3rem 0;
    padding: 4rem 0;
    background-size: contain;
    background-repeat: no-repeat;
    position: relative;
    overflow: hidden;
    h2 {
        font-family: 'Dancing Script Variable', sans-serif;
        color: $title-color;
        font-size: 3rem
    }
    h3{
        font-size: 1.6rem;
    }
    .wrapper {
        @include flex(center, center, column);
        .row{
            margin-top: 2rem
        }
        .col{
            @include flex(center, center, row);
        }   
        
    }
    .maxcoach-shape-13 {
        position: absolute;
        right: -70px;
        top: 50%;
        z-index: -1;
    }
    .artist-shape-01{
        position: absolute;
        transform: rotate(270deg);
        left: -50px;
        top: 0px;
        height: 520px;
        z-index: -1;
    }
}
</style>