<script>

export default {
    data() {
        return {
            bgImg1: "maxcoach-shape-12-150x150.png",
            bgImg2: "maxcoach-shape-14.png",
            bgImg3: "orange_circle.svg",
        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/blog/${imgName}`, import.meta.url).href;
        },
    },      
}
</script>

<template>
    <section>
        <div class="container-m">
            <div class="title">
                <h2>Articles and Tips</h2>
                <h3>Latest Form The Blog</h3>
            </div>
            <div class="row">
                <div class="col">
                    <div class="card card-small down">
                        <div>
                            <img :src="getImgPath('artist-blog-03-480x356.jpeg')" alt="">
                        </div>
                        <div class="card-text shadow">
                            <p>ARTIST</p>
                            <h4>Brush Strokes Energize Trees in Paintings</h4>
                            <div class="info">
                                <span><i class="fa-regular fa-calendar"></i> May 15, 2020</span>
                                <span><i class="fa-regular fa-eye"></i> 688</span>
                            </div>
                        </div>
                    </div>
                    <div class="card card-large">
                        <div class="img-w">
                            <img :src="getImgPath('artist-blog-02-500x680.jpg')" alt="">
                            <div class="card-text">
                                <p>ARTIST</p>
                                <h4>Connection Between Self-Portraits and Identity</h4>
                                <div class="info">
                                    <span><i class="fa-regular fa-calendar"></i> May 15, 2020</span>
                                    <span><i class="fa-regular fa-eye"></i> 387</span>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="card card-small up">
                        <div>
                            <img :src="getImgPath('artist-blog-01-480x356.jpg')" alt="">
                        </div>
                        <div class="card-text shadow">
                            <p>ARTIST</p>
                            <h4>Poket-Sized Notebooks Hold Miniatures Paintings</h4>
                            <div class="info">
                                <span><i class="fa-regular fa-calendar"></i> May 15, 2020</span>
                                <span><i class="fa-regular fa-eye"></i> 603</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="link">
                <p>Get into detalis now? 
                    <a href="">
                        View all posts <i class="fa-solid fa-arrow-right"></i>
                    </a>
                </p>
            </div>
        </div>
        <img :src="getImgPath(bgImg1)" class="dots" alt="">
        <img :src="getImgPath(bgImg2)" class="line" alt="">
        <img :src="getImgPath(bgImg3)" class="circle" alt="">
    </section>
</template>

<style scoped lang="scss"> 
@use "../style/partials/mixin" as *;
 @use "../style/partials/variables" as *;

 section {
     background-color: #f5f7fa;
     padding: 4rem 0;
     position: relative;
     z-index: 1;
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

     .col{
        @include flex(center, center, row);
        margin: 2rem;
        gap: 40px;
        position: relative;
        z-index: 1;
     }
     .card-small {
        width: 300px;
        img{
            width: 300px;
            display: block;
        }
        p{
            color: gray;
            padding-top: 1rem;
            padding-bottom: 0.5rem;
        }
        h4{
            line-height: 2rem;
            font-size: 1.2rem;
            padding-bottom: 0.5rem;
        }
        .info{
            @include flex(space-between, center, row)
        }
        .card-text {
            padding: 1rem;
            background-color: white;
        }
     }
     .card-large {
        .img-w {
            position: relative;
            .card-text {
                position: absolute;
                bottom: 10%;
                padding: 0 2rem;
                color: white;
                h4{
                    font-size: 1.6rem;
                    line-height: 2.5rem;
                    margin: 1rem 0;

                }
            }
        }
     }
     .link{
        text-align: center;
        p{
            color: gray;
            a {
                color: $btn-bg;
                font-weight: bold;
                border-bottom: 1px solid rgb(206, 206, 206);
            }
        }
     }
     .dots{
        position: absolute;
        z-index: 0;
        top: 20%;
        left: 35%;
     }
     .line{
        position: absolute;
        z-index: 0;
        top: 50%;
        left: 0;
        transform: translateY(-50%);
     }
     .circle{
        position: absolute;
        z-index: 0;
        opacity: 30%;
        width: 100px;
        top: 20%;
        left: 15%;
     }
     .up{
        position: absolute;
        top: 100px;
        right: -120px;
     }
     .down{
        position: absolute;
        bottom: 100px;
        left: -120px;
     }
 }
 </style>