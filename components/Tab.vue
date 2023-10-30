<template>
    <div class="tab-content text-white" v-show="title == selectedTitle">
        <CircleTree/>
        <slot/>
    </div>
</template>

<script>
import { inject } from 'vue'
import CircleTree  from '@/components/CircleTree.vue'

    export default {
        props: ['title'],
        setup() {
            const selectedTitle = inject("selectedTitle")

            return {
                selectedTitle
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>