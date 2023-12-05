<script>
export default {
    data() {
        return {
            imgArray: [
                {
                    path: "artist-video-poster.jpg",
                    class: "artist-video",
                },
                {
                    path: "icon-youtube-play.png",
                    class: "icon-youtube",
                },
                {
                    path: "maxcoach-shape-05.png",
                    class: "maxcoach-shape-05",
                },
                {
                    path: "maxcoach-shape-12-150x150.png",
                    class: "maxcoach-shape-12",
                },
                {
                    path: "maxcoach-shape-13.png",
                    class: "maxcoach-shape-13",
                },
                {
                    path: "artist-shape-color-paint-bottom-right.png",
                    class: "artist-shape-color",
                },
                {
                    path: "artist-shape-color-paint-bottom-right.png",
                    class: "artist-shape-color-1",
                },

                
            ],
        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/videoimg/${imgName}`, import.meta.url).href;
        }
    },

}
</script>

<template>
<section>
    <img v-for="img in imgArray" :src="getImgPath(img.path)" :class="img.class" :key="img.class" alt="">
</section>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;

section {
    padding: 4rem 0;
    position: relative;
    @include flex (center, center, row);
    .artist-video {
        z-index: 1;
    }
    .icon-youtube{
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
        z-index: 2;
    }
    .maxcoach-shape-05{
        position: absolute;
        top: 5%;
        left: 15%;
    }
    .maxcoach-shape-12{
        position: absolute;
        bottom: 5%;
        right: 15%;
    }
    .maxcoach-shape-13{
        position: absolute;
        bottom: 40%;
        right: 15%;
        width: 100px;
    }
    .artist-shape-color {
        position: absolute;
        bottom: 5%;
        left: 15%;
        z-index: 2;
        transform: scaleX(-1);
        z-index: 0;
    }
    .artist-shape-color-1 {
        position: absolute;
        top: 5%;
        right: 15%;
        z-index: 2;
        z-index: 0;
        transform: scaleX(-1);
        transform: rotate(40deg);
    }

}
</style>