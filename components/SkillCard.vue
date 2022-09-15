<template>
    <div class="w-full border border-greyish rounded-xl p-5">
        <div class="flex flex-col space-y-4 justify-center items-center">
            <font-awesome-layers class="fa-4x" fixed-width>
                <font-awesome-icon icon="fa-solid fa-circle" />
                <font-awesome-icon :icon="`fa-solid ${skill.icon}`" transform="shrink-6" class="text-dark" />
            </font-awesome-layers>
            <h2 class="text-center text-orange">
                {{ skill.title }}
            </h2>
            <div class="flex flex-col space-y-1 pt-4">
                <p 
                    v-for="type, index in skill.list"
                    :key="index"
                    class="uppercase text-center font-roboto text-ghost tracking-widest"
                    :class="fontWeights[index]"
                >
                    {{ type }}
                </p>
            </div>
        </div>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    name: 'SkillCard',
    props: {
        skill: {
            type: Object,
            required: true
        },
    },
    data() {
        return {
            fontWeights: [
                'font-black',
                'font-extrabold',
                'font-bold',
                'font-semibold',
                'font-medium',
                'font-normal',
                'font-light',
                'font-extralight',
                'font-thin',
            ]
        }
    },
})
</script>