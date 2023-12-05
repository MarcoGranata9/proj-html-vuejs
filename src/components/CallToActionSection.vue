<script>
export default {
    data() {
        return {
            imgQuote: "artist-quote-icon.png"
        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/${imgName}`, import.meta.url).href;
        }
    },
}
</script>

<template>
<section>
    <div class="container-m">
        <div class="row">
            <div class="col title">
                <div class="card">
                    <img :src="getImgPath(imgQuote)" alt="">
                    <h2>I coach and mentor visual aritsts, like you, to Create Like You Mean It</h2>
                    <p>Martin Garrix</p>
                </div>
            </div>
            <div class="col text">
                <div class="card">
                    <p>As a coach and mentor, my ultimate goal is to motivate visual artists toward inspired action. I help you get you back on track to being the productive, creative, meaningful and authentic artist you truly want to be.l support artists in crafting and living a creative life as well as feeling good about themselves and their art.</p>
                    <p>As an artist and an educator for nearly 30 years, I understand what it takes to create.</p>
                    <button class="btn-light">Get started today</button>
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
    padding: 4rem 0;
}
.row {
    @include flex(space-between, center, row);
    
    .col.title {
        text-align: center;
        width: 40%;
        h2 {
            font-size: 3rem;
            margin-bottom: 2rem;
        }
        p {
            font-family: 'Dancing Script Variable', sans-serif;
            color: $title-color;
            font-size: 3rem;
        }     
    }
    .col.text{
        width: 50%;
        p{
            line-height: 2rem;
            margin-bottom: 2rem;
        }
        .btn-light{
            padding: 1rem 2rem
        }
    }
}
</style>