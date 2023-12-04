<script>
export default {
    data() {
        return {
            imgNameHero: [
                {
                    path: "artist-hero-image-01.jpg",
                    class: "hero-image-01"
                },
                {
                    path: "artist-hero-image-02.jpg",
                    class: "hero-image-02"
                },
                {
                    path: "artist-hero-image-03.png",
                    class: "hero-image-03"
                },
                {
                    path: "artist-hero-image-04.jpg",
                    class: "hero-image-04"
                },
                {
                    path: "artist-shape-01.png",
                    class: "artist-shape-01"
                },
                {
                    path: "artist-shape-02.png",
                    class: "artist-shape-02"
                },
                {
                    path: "artist-shape-03.png",
                    class: "artist-shape-03"
                },
                {
                    path: "artist-shape-04.png",
                    class: "artist-shape-04"
                },
                {
                    path: "artist-shape-05.png",
                    class: "artist-shape-05"
                },
                {
                    path: "maxcoach-shape-12.png",
                    class: "maxcoach-shape-12"
                },
            ],
        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/hero/${imgName}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <div class="hero">
        <div class="text">
            <h1>Hello, Im Martin</h1>
            <h2>Artist Coaching And Mentoring <br> Might Be For You.</h2>
            <button class="btn">Get started today</button>
        </div>
        <img v-for="img in imgNameHero" :src="getImgPath(img.path)" :class="img.class" alt="">
    </div>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;
.hero{
    position: relative;
    min-height: 700px;  
    background-color: #fbf9f6;
    @include flex(center, center, column);
    .text{
        z-index: 5;
        h1 {
            font-family: 'Dancing Script Variable', sans-serif;
            color: $title-color;
            font-size: 3.5rem;
        }
        h2 {
        text-align: center;
        font-size: 2rem;
        margin-bottom: 2rem
        }
        .btn{
            padding: 1rem 2rem
        }
        @include flex(center, center, column);
        .img-text {
            width: 400px;
        }
    }
    
    .hero-image-01 {
        position: absolute;
        bottom: 10%;
        left: 5%;
        z-index: 2;
    }
    .hero-image-02 {
        position: absolute;
        bottom: 40%;
        left: 13%;
        z-index: 1;
    }
    .hero-image-03 {
        position: absolute;
        bottom: 5%;
        left: 24%;
    }
    .hero-image-04 {
        position: absolute;
        bottom: 10%;
        right: 10%;
        z-index: 1;
        width: 300px;
    }         
    .artist-shape-01 {
        position: absolute;
        top: 0;
        right: 40px;
    }
    .artist-shape-02 {
        position: absolute;
        top: 0;
        left: 0;
        width: 800px;
    }
    .artist-shape-03 {
        position: absolute;
        top: 20%;
        left: 1%;
        width: 300px;
    }
    .artist-shape-04 {
        position: absolute;
        top: 70px;
        right: 5%;
    }
    .artist-shape-05 {
        position: absolute;
        bottom: 0;
        right: 0;
    }
    .maxcoach-shape-12 {
        position: absolute;
        bottom: 2%;
        right: 20%;
    }
    .hero-image-01 .hero-image-02 .hero-image-04 {
        box-shadow: 5px 5px 0px 0px;
    }
}
</style>