<script>
export default {
    data() {
        return {
            img1: "artist-shape-color-paint-bottom-right.png",
            img2: "artist-shape-color-paint-top-left.png",
        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/${imgName}`, import.meta.url).href;
        },
    }
}
</script>

<template>
    <section>
        <div class="container-m">
            <!-- <div class="wrapper"> -->
                <h2>Newsletter to get in touch</h2>
                <div class="input-email">
                    <label for="email">Insert your email</label>
                    <input placeholder="Your e-mail" id="email" type="email">
                    <i class="fa-solid fa-arrow-right"></i>
                </div>
            <!-- </div> -->
        </div>
        <img class="right" :src="getImgPath(img1)" alt="">
        <img class="left" :src="getImgPath(img2)" alt="">
    </section>
</template>

<style scoped lang="scss"> 
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

section {
    background-color: #244186;
    position: relative;
    min-height: 200px;
    
    .container-m {
        position: relative;
        z-index: 1;
        @include flex(space-between, center, row);
        min-height: 200px;
        width: 60%;
        .input-email {
            width: 60%;
            position: relative;
        }
        h2 {
            color: white;
        }
        input {
            border: none;
            border-bottom: 2px solid #5b71a4;
            background-color: transparent;
            padding: 1rem;
            font-size: 1.5rem;
            width: 100%;
            &::placeholder{
                color: white;
            }
            &:focus-visible{
                outline: solid rgba($color: #ffffff, $alpha: 0.5);
                border-radius: 10px;
            }
        }
        i{
            font-size: 2rem;
            color: white;
            position: absolute;
            right: 0;
            top: 50%;
            transform: translateY(-50%);
            &:hover{
                cursor: pointer;
            }
        }
    }
}
.right {
    position: absolute;
    bottom: 0;
    right: 0;
    z-index: 0;
}
.left {
    position: absolute;
    top: 0;
    left: 0;
    height: 200px;
    z-index: 0;
}
img {
    width: 300px;
}
label{
    display: none;
}
</style>