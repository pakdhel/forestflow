<template>
    <div class="flex justify-center translate-y-[60px]">
        <div class="w-[150px] h-[50px] px-[37px] py-[15px] bg-slate-400 rounded-[20px] justify-center items-center gap-2.5 inline-flex mr-2">
            <button class="text-cyan-950 text-[25px] font-semibold font-['Inter']" 
            @click="resetTimer">
                RESET
            </button>
        </div>
    </div>
</template>

<script>
    export default {
        methods: {
            resetTimer() {
                this.$emit('reset-timer')
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>