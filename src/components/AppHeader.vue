<script>
export default {
    data() {
        return {

        }
    },
    methods: {
        getImgPath(imgName) {
            return new URL(`../assets/img/${imgName}`, import.meta.url).href;
        }
    },
    props: {
        headerProps: Object
    }
}
</script>

<template>
    <header>
        <div class="container">
            <div class="wrapper">
                <div class="logo">
                    <img src="../assets/img/dark-logo.png" alt="">
                </div>
                <div class="nav">
                    <ul>
                        <li v-for="elem in headerProps.navArray">
                            <a href="">{{ elem }} <i
                            class="fa-solid fa-chevron-down"></i></a>
                        </li>
                    </ul>
                </div>
                <div class="social">
                    <ul>
                        <li v-for="elem in headerProps.socialArray"><a href="" v-html="elem"></a></li>
                    </ul>
                </div>
            </div>
        </div>
    </header>
</template>

<style scoped lang="scss">
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;

header { 
    height: 100px;
    .container {
        height: 100%
    }
    .wrapper {
        @include flex(space-between, center, row);
        height: 100%;
        ul {
            @include flex(space-between, center, row);
            gap: 1rem;
        }

        a:hover{
            opacity: 70%;
        }
    }

    .logo{
        img {
            width: 200px;
        }
    }

    .nav {
        a{
            @include flex(center, center, row);
            gap: 0.3rem;        
        }
        i {
            font-size: 0.5rem
        }
    }
   
    .social {
        a {
            font-size: 1.2rem;
            color: $gray-cube;
        }
    }
}
</style>
