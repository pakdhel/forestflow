<template>
    <div class="bg-cover bg-center h-screen" style="background-image: url('https://images.unsplash.com/photo-1534269222346-5a896154c41d?auto=format&fit=crop&q=80&w=2070&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');">
        <Points/>
        <TabsWrapper>
            <Tab title="Pomodoro">
                <PomodoroTimer :minutes="minutes = 25" :seconds="seconds = 0"/>
            </Tab>
            <Tab title="Break">
                <PomodoroTimer :minutes="minutes = 5" :seconds="seconds = 0"/>
            </Tab>
            <Tab title="Long Break">
                <PomodoroTimer :minutes="15" :seconds="0"/>
            </Tab>
        </TabsWrapper>

        <div class="btn flex justify-center">
            <ButtonStartStop />
            <ButtonReset />
        </div>
    </div>
</template>

<script>
import TabsWrapper from '@/components/TabsWrapper.vue'
import Tab from '@/components/Tab.vue'
import Points from '@/components/Points.vue'
import PomodoroTimer from '@/components/PomodoroTimer.vue'
import ButtonStartStop from '@/components/Button/ButtonStartStop.vue'
import ButtonReset from '@/components/Button/ButtonReset.vue'
    export default {
        data() {
            return {
                minutes: Number,
                seconds: Number,
                timer: null,
                isRunning: false
            }
        },

        methods: {

        }
    }
    
</script>

<style lang="scss" scoped>

</style>