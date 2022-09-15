<template>
    <div
        class="z-50 bg-dark sticky top-0 left-0 right-0 border-b-0.5 border-greyish h-12 md:h-16 lg:h-24 flex items-center justify-between mx-auto bg-dark"
    >
        <WawyTitle
            class="ml-10"
            :title="title" 
        />
        <!-- mobile menu -->
        <div class="lg:hidden relative flex h-full">
            <font-awesome-icon 
                icon="fa-solid fa-burger"
                size="2x"
                class="cursor-pointer mr-10 self-center"
                @click="toggleMenu"
            />
            <transition name="fade">
                <nav
                    v-if="isMenuOpen"
                    class="flex flex-col space-y-4 p-4 w-44 text-center absolute right-0 top-12 md:top-16 rounded-bl border-l-0.5 border-b-0.5 border-greyish bg-dark text-ghost shadow-2xl"
                >
                    <NuxtLink to="/" class="link-turquoise">
                        A propos
                    </NuxtLink>
                    <NuxtLink to="/blog" class="link-turquoise">
                        Blog
                    </NuxtLink>
                    <div class="flex justify-evenly">
                        <a 
                            href="https://github.com/wild-e/wild-e.github.io" 
                            target="_blank"
                        >
                            <font-awesome-icon icon="fa-solid fa-code" size="xl" class="link-turquoise"/>
                        </a>
                        <a 
                            href="https://www.linkedin.com/in/wild-e/" 
                            target="_blank"
                        >
                            <font-awesome-icon :icon="['fab', 'linkedin']" size="xl" class="link-turquoise"/>
                        </a>
                        <a 
                            href="https://github.com/wild-e" 
                            target="_blank"
                        >
                            <font-awesome-icon :icon="['fab', 'github']"  size="xl" class="link-turquoise"/>
                        </a>
                    </div>

                </nav>
            </transition>
        </div>
        <!-- desktop menu -->
        <nav
            class="space-x-6 hidden lg:flex font-bold mr-10"
        >
            <NuxtLink to="/" class="link-turquoise">
                A propos
            </NuxtLink>
            <NuxtLink to="/blog" class="link-turquoise">
                Blog
            </NuxtLink>
            <a 
                href="https://github.com/wild-e/wild-e.github.io" 
                target="_blank"
            >
                <font-awesome-icon icon="fa-solid fa-code" size="lg" class="link-turquoise"/>
            </a>
            <a 
                href="https://www.linkedin.com/in/wild-e/" 
                target="_blank"
            >
                <font-awesome-icon :icon="['fab', 'linkedin']" size="lg" class="link-turquoise"/>
            </a>
            <a 
                href="https://github.com/wild-e" 
                target="_blank"
            >
                <font-awesome-icon :icon="['fab', 'github']" size="lg" class="link-turquoise"/>
            </a>

        </nav>
    </div>
</template>

<script>
export default {
    name: 'TheHeader',
    data() {
        return {
            title: 'wild[e].dev',
            isMenuOpen: false
        }
    },
    methods: {
        toggleMenu() {
            this.isMenuOpen = !this.isMenuOpen
        }
    }
}
</script>

<style>
    .fade-enter-active, .fade-leave-active {
        transition: ease-in-out opacity 0.3s;
    }
    .fade-enter, .fade-leave-to {
        opacity: 0;
    }
</style>
