<template>
    <div class="bg-cover bg-center h-screen" style="background-image: url('https://images.unsplash.com/photo-1534269222346-5a896154c41d?auto=format&fit=crop&q=80&w=2070&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D');">
        <Points/>
        <TabsWrapper>
            <Tab title="Pomodoro">
                <PomodoroTimer />
            </Tab>
            <Tab title="Break">
                <BreakTimer />
            </Tab>
            <Tab title="Long Break">
                <LongBreakTimer />
            </Tab>
        </TabsWrapper>

        <audio controls loop class="ml-4 mt-10 w-[250px] h-[40px]">
            <source src="../assets/sounds/lofi-rain.mp3" type="audio/mpeg">
        </audio>

    </div> 
</template>

<script>
import TabsWrapper from '@/components/TabsWrapper.vue'
import Tab from '@/components/Tab.vue'
import Points from '@/components/Points.vue'
import PomodoroTimer from '@/components/PomodoroTimer.vue'

    export default {
        
    }
    
</script>

<style lang="scss" scoped>

</style>