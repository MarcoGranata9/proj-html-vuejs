<script>
export default {
    data() {
        return {
            countdown: null 
        }
    },
    methods: {
        countdownfun() {
            let countDownDate = new Date(new Date().getTime() + 86400000).getTime();
            this.countdown = setInterval(function(){
                let now = new Date().getTime();
                let difference = countDownDate - now;
                let days = Math.floor(difference / (1000 * 60 * 60 * 24));
                let hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                let minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));
                let seconds = Math.floor((difference % (1000 * 60)) / 1000);
                
                document.getElementById("counter").innerHTML = days + "d " + hours + "h "
                + minutes + "m " + seconds + "s ";

                if (difference < 0) {
                    clearInterval(this.countdown);
                    document.getElementById("counter").innerHTML = "Countdown finito";
                }
            }, 1000)
        }
    }
}
</script>

<template>
    <div class="header-top">
        <div class="container">
            <div class="timer-wrapper">
                <p>Starts TOMORROW! Our biggest event of the year...</p>
                <div class="timer"><i class="fa-regular fa-clock"></i><span id="counter">{{ countdownfun() }}</span></div>
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

        .timer-wrapper {
            @include flex(space-between, center, row);
            padding: 15px 0;

            p {
                color: #7d7d7d;
                font-size: 0.9rem;
            }

            .timer {
                color: #3f4369;
                font-weight: bold;
            }
        }
    }
}</style>