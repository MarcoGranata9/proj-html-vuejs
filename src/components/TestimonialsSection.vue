<script>
import TestimonialsCard from "./TestimonialsCard.vue";

export default {
    data() {
        return {
            cardArray: [
                {
                    img: "artist-testimonial-avatar-01.jpg",
                    title: "It's a choice of quality for people with special needs",
                    text: "I'm a very strict person so I require everything to be organized and neat. Then, I'll be able to make things right and shine. MaxCoach guys just got me.",
                    name: "Florence Themes",
                    job: "Multimedia Admin",
                },
                {
                    img: "artist-testimonial-avatar-04.jpg",
                    title: "High level of efficiency and scientific teaching methods",
                    text: "I am free to learn at my own pace, follow my own schedule and choose the subject I want to learn from the syllabus. Great study portal for people like me.",
                    name: "Mina Hollace",
                    job: "Freelancer",
                    class: "active"
                },
                {
                    img: "artist-testimonial-avatar-03.jpg",
                    title: "Professional team of specialists and passionate mentors at reach",
                    text: "I need to get a certification for English proficiency and MaxCoach is my best choice. Their tutors are smart and professional when dealing with students.",
                    name: "Madley Pondor",
                    job: "IT Specialist",
                },
            ],          
        }
    },
    components: {TestimonialsCard}
}
</script>

<template>
<section>
    <div class="title">
        <h2>Testimonials</h2>
        <h3>Why do people love me?</h3>
    </div>

    <div class="row">
        <div class="col" v-for="card in cardArray">
            <TestimonialsCard  :card="card"/>
        </div>
    </div>

    <div class="counter">
        <i class="fa-solid fa-circle"></i>
        <i class="fa-regular fa-circle"></i>
        <i class="fa-regular fa-circle"></i>
        <i class="fa-regular fa-circle"></i>
    </div>
</section>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;
section {
    background-color: #faf8f6;
    padding: 4rem 0;
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
    .row {
            @include flex(space-between, center, row);
            flex-wrap: nowrap;
            .col {
                width: calc(100% / 3);
                padding: 2rem;
            }
        }
    .counter {
        text-align: center;
        i {
            margin: 0 1rem;
        }
    }
    .active {
        opacity: 100%;
    }
}
</style>