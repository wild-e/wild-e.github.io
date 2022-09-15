<template>
    <h4
        class="flex items-center select-none cursor-default font-semibold"
        :class="styling && styling"
    >
        <span 
            v-for="letter, index in title" 
            :key="index" 
            :ref="index"
            @mouseenter="onMouseenter(index)"
        >
            {{letter}}
        </span>
    </h4>
</template>

<script>
export default {
    name: 'WawyTitle',
    props: {
        title: {
            type: String,
            required: true
        },
        styling: {
            type: String,
            required: false,
            default: "text-ghost lg:text-6xl md:text-4xl text-xl"
        }
    },
    methods: {
        onMouseenter(index) {
            this.$refs[index][0].classList.add('upAndDown')
            setTimeout(() => {
                this.$refs[index][0].classList.remove('upAndDown')
            }, 1000)
        }
    }
}
</script>

<style>
.upAndDown{
    position: relative;
    display: inline-block;
    animation: upAndDown 1s 1 ease-in-out;  
}
@keyframes upAndDown {
    0%,40%,100% {
        transform: translateY(0)
    }
    20% {
        transform: translateY(-10px)
    }
    50% {
        transform: translateY(2px)
    }
    65% {
        transform: translateY(-1px)
    }
}
</style>