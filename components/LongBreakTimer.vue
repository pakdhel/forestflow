<template>
    <div>
        <div class="flex items-center justify-center translate-y-[40px]">
            <div class="w-[341px] h-[100px] px-[58px] py-[8px] bg-[#003530] rounded-[20px] border border-neutral-400 border-opacity-10 backdrop-blur-[19.60px] justify-center items-center gap-2.5 inline-flex">
                <div class="text-[#aee3ac] text-7xl font-semibold font-['Inter']">25:00</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            minutes: Number,
            seconds: Number
        },

        computed: {
            minutesDislay() {
                return String(this.minutes).padStart(2, "0");
            },
            secondsDislay() {
                return String(this.minutes).padStart(2, "0");
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>