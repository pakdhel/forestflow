<template>
    <div>
        <div class="flex items-center justify-center translate-y-[40px]">
            <div class="w-[341px] h-[100px] px-[58px] py-[8px] bg-[#003530] rounded-[20px] border border-neutral-400 border-opacity-10 backdrop-blur-[19.60px] justify-center items-center gap-2.5 inline-flex">
                <div class="text-[#aee3ac] text-7xl font-semibold font-['Inter']">{{ minutesDislay }}:{{ secondsDislay }}</div>
            </div>
        </div>

        <div class="btn flex justify-center">
            <ButtonStartStop :isRunning="isRunning" @toggle-timer="toggleTimer"/>
            <ButtonReset @reset-timer="resetTimer"/>
        </div>

        <audio ref="myAudio">
            <source src="../assets/sounds/alarm-clock.mp3" type="audio/mpeg">
        </audio>
        
    </div>
</template>

<script>

    export default {
        data() {
            return {
                isRunning: false,
                timer: null,
                minutes:25,
                seconds: 0,
                counter: 0,
            }
        },

        computed: {
            minutesDislay() {
                return String(this.minutes).padStart(2, "0");
            },
            secondsDislay() {
                return String(this.seconds).padStart(2, "0");
            }
        },

        methods: {
            starTimer() {
                if (!this.isRunning) {
                    this.timer = setInterval(() => {
                        if (this.minutes === 0 && this.seconds ===0 ) {
                            this.counter = this.counter + 5;
                            this.sendCounter();
                            console.log(this.counter);
                            this.stopTimer();
                            this.resetTimer();

                            const audioElement = this.$refs.myAudio;
                            console.log(audioElement);

                            audioElement.play();
                        } else if (this.seconds === 0) {
                            this.minutes--;
                            this.seconds = 59;
                        } else {
                            this.seconds--;
                        }
                    }, 1000);
                    this.isRunning = true
                }
            },

            stopTimer() {
                clearInterval(this.timer);
                this.isRunning = false;
            },

            resetTimer() {
                this.stopTimer();
                this.minutes = 25;
                this.seconds = 0;
                clearInterval(this.timer);
                this.isRunning = false;
            },  

            toggleTimer() {
                console.log('u clicked me');
                if (this.isRunning) {
                    this.stopTimer();
                } else {
                    this.starTimer();
                }
            },

            sendCounter() {
                this.$emit('counter', this.counter);
            },
        }
    }
</script>

<style lang="scss" scoped>

</style>