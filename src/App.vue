<script>
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';

export default {
    data() {
        return {
            headerProps: {
                navArray: ["Home", "Pages", "Courses", "Features", "Blog", "Shop"],
                socialArray: ['<i class="fa-brands fa-twitter"></i>', '<i class="fa-brands fa-facebook-f"></i>', '<i class="fa-brands fa-instagram"></i>','<i class="fa-brands fa-linkedin"></i>',],
            },
            footerProps: {
                socialArray: ['<i class="fa-brands fa-twitter"></i>', '<i class="fa-brands fa-facebook-f"></i>', '<i class="fa-brands fa-instagram"></i>','<i class="fa-brands fa-linkedin"></i>',],
                explore: ["Start here", "Success story", "Blog", "Contact Us"],
                info: ["Membership", "Purchase guide", "Privacy policy", "Terms of services"],
                instagram: ["footer-img-1.jpg", "footer-img-2.jpg", "footer-img-3.jpg"]
            }
        } 
    },
    components: { AppHeader, AppMain, AppFooter },
     
}
</script>

<template>
<AppHeader :headerProps="headerProps"/>
<AppMain/>
<AppFooter :footerProps="footerProps"/>
</template>

<style lang="scss">
@use "./style/general.scss";
@import "@fortawesome/fontawesome-free/css/all.css";
// Supports weights 400-700
@import '@fontsource-variable/dancing-script';
</style>
