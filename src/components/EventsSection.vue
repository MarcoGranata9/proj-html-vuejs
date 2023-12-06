<script>
import EventsCard from './EventsCard.vue';

export default {
    data() {
        return {
            cardArray: [
                {
                    img: "artist-event-04-250x300.jpg",
                    date: "NOV 22, 2020", 
                    title: "Storytelling Workshop",
                    location: "Texas, US",
                },
                {
                    img: "artist-event-03-250x300.jpg",
                    date: "OCT 10, 2020", 
                    title: "Painting Art Contest 2020",
                    location: "New York, US",
                },
                {
                    img: "artist-event-02-250x300.jpg",
                    date: "NOV 23, 2020", 
                    title: "International Art Fair 2020",
                    location: "Hambourg, Germany",
                    class: "reverse"
                },
                {
                    img: "artist-event-01-250x300.jpg",
                    date: "DEC 15 2020", 
                    title: "Street performance: Call For Artist",
                    location: "Illinois, US",
                    class: "reverse"
                }

            ],
            bgimg1: "artist-shape-02-600x324.png",
            bgimg2: "maxcoach-shape-13.png",   
        };
    },
    components: { EventsCard },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/${imgName}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <section>
        <div class="container-m">
            <div class="title">
                <h2>Upcoming Events</h2>
                <h3>Let's work together</h3>
            </div>
    
            <div class="row">
                <div class="col">
                    <EventsCard v-for="card in cardArray" :card="card"/>
                </div>
            </div>
        </div>
        <img :src="getImgPath(bgimg1)" class="bg-1" alt="">
        <img :src="getImgPath(bgimg2)" class="bg-2" alt="">
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
        h3 {
            font-size: 2rem;
        }
    } 
    .col {
        @include flex(space-between, center, row);
        flex-wrap: wrap;
        gap: 20px;
        .reverse {
            flex-direction: row-reverse;
        }
    }
    .row{
        margin-top: 4rem;
    }
    .bg-1{
        position: absolute;
        transform: rotate(270deg);
        z-index: 0;
        left: -140px;
        bottom: 130px;
    }
    .bg-2 {
        position: absolute;
        top: 100px;
        right: -40px;
        z-index: 0;
    }
}
</style>