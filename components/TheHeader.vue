<template>
    <div
        class="bg-dark sticky top-0 left-0 right-0 border-b-0.5 border-greyish py-5 px-10 flex items-center justify-between mx-auto bg-dark"
    >
        <h1
            class="flex items-center select-none cursor-default text-ghost text-6xl"
        >
            <p 
                v-for="letter, index in title" 
                :key="index" 
                :ref="index"
                @mouseenter="onMouseenter(index)"
            >
                {{letter}}
            </p>
        </h1>

        <nav class="space-x-4 flex items-end">
            <NuxtLink to="/" class="link-turquoise">
                Home
            </NuxtLink>
            <NuxtLink to="/a-propos" class="link-turquoise">
                A propos
            </NuxtLink>
            <NuxtLink to="/blog" class="link-turquoise">
                Blog
            </NuxtLink>
            <a 
                href="https://github.com/wild-e/wild-e.github.io" 
                target="_blank"
            >
                <font-awesome-icon icon="fa-solid fa-code" class="link-turquoise"/>
            </a>
            <a 
                href="https://www.linkedin.com/in/wild-e/" 
                target="_blank"
            >
                <font-awesome-icon :icon="['fab', 'linkedin']" class="link-turquoise"/>
            </a>
            <a 
                href="https://github.com/wild-e" 
                target="_blank"
            >
                <font-awesome-icon :icon="['fab', 'github']" class="link-turquoise"/>
            </a>

        </nav>
    </div>
</template>

<script>
export default {
    name: 'TheHeader',
    data() {
        return {
            title: 'wild[e].dev'
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
.roboto {
    font-family: 'Roboto', sans-serif;
}
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