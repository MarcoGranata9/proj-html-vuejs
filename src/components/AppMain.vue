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
    }
}

</script>

<template>

</template>

<style scoped lang="scss">

</style>
