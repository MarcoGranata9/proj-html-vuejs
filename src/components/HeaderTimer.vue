<script>
export default {

}
</script>

<template>
    <div class="header-top">
        <div class="container">
            <div class="timer-wrapper">
                <p>Starts TOMORROW! Our biggest event of the year...</p>
                <div class="timer"><i class="fa-regular fa-clock"></i> 00 : 00 : 00 : 00</div>
                <button class="btn">Get ticket</button>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;
.header-top {
    background-color: $gray-bg;
    .container {
        width: 50%;
        max-width: 800px;
        .timer-wrapper{
            @include flex(space-between, center, row);
            padding: 15px 0;
            p{
                color: #7d7d7d;
                font-size: 0.9rem;
            }
            .timer {
                color: #3f4369;
                font-weight: bold;
            }
        }
    }
}
</style>