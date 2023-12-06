<script>
export default {
    data() {
        return {

        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/footer/${imgName}`, import.meta.url).href;
        }
    },
    props: {
        footerProps: Object
    }
}

</script>

<template>
    <footer>
        <div class="container">
            <div class="row">
                <div class="col">
                    <h4>Address</h4>
                    <p>382 NE 191st ST # 87394 Miami, FL 33179-3889</p>
                    <p>+1(414)234-6163(9am - 5pm EST, Monday - Friday)</p>
                    <p>support@maxcoach.com</p>
                    <ul class="social">
                        <li v-for="elem in footerProps.socialArray"><a href="" v-html="elem"></a></li>
                    </ul>
                </div>
                <div class="col col-center">
                    <ul class="card">
                        <li><h4>Explore</h4></li>
                        <li v-for="elem in footerProps.explore"><a href="">{{ elem }}</a></li>
                        
                    </ul>
                    <ul class="card">
                        <li><h4>Information</h4></li>
                        <li v-for="elem in footerProps.info"><a href="">{{ elem }}</a></li>
                    </ul>
                </div>
                <div class="col col-img">
                    <h4>Instagram <span>@maxcoach</span></h4>
                    <div class="img">
                        <img v-for="img in footerProps.instagram" :src="getImgPath(img)" alt="">
                    </div>
                </div>
            </div>
            <p class="copy">&copy 2020 Maxcoach. All Rights Reserved</p>
        </div>
    </footer>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

footer {
    padding: 4rem 0;
    .row {
        @include flex(space-between, start, row);
        gap: 20px;
    }
    .col{
        width: calc(100% / 3 - 40px);
        h4 {
            font-size: 1.1rem;
            line-height: 2rem;
            margin-bottom: 1rem;
            color: black;
        }
        p {
            line-height: 2.5rem;
            font-size: 0.9rem;
            color: rgb(98, 98, 98);
        }
        li {
            line-height: 2.5rem;
            font-size: 0.9rem;
            color:  rgb(98, 98, 98);
        }
        .social{
            @include flex(start, center, row);
            margin-top: 2rem;
            a{
                margin-right: 2rem;
                font-size: 1.5rem;
                color: rgb(170, 170, 170);
            }
        }
    }
    .col-center{
        @include flex(space-between, center, row);
    }
    .col-img{
        img{
            width: 120px;
        }
        .img{
            @include flex(space-between, center, row);
        }
        span {
            color: $btn-bg;
            font-weight: normal;
        }
    }
    .copy{
        text-align: center;
        color: rgb(98, 98, 98);
        padding-top: 4rem;
        font-size: 0.9rem;
    }
}
</style>
