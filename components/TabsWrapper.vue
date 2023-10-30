<template>
    <div class="tabs">
        <ul class="tabs_header text-white flex justify-center mb-4 mt-2">
            <li class="mr-3 ml-3 bg-[#003530] rounded-[50px] p-[10px]"
            v-for="title in tabTitles" 
            :key="title"
            @click="selectedTitle = title"
            :class="{ 'bg-[#eee] text-[#000]': selectedTitle === title }"
            >
                {{ title }}
            </li>
        </ul>
        <slot/>
    </div>
</template>

<script>
import { ref, provide } from 'vue'
    export default {
        setup(props, { slots }) {
            const tabTitles = ref(slots.default().map((tab) => tab.props.title))
            const selectedTitle = ref(tabTitles.value[0])

            provide("selectedTitle", selectedTitle)

            return {
                tabTitles,
                selectedTitle
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>