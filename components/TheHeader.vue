<template>
    <div
        class="z-50 bg-dark sticky top-0 left-0 right-0 border-b-0.5 border-greyish py-5 px-10 flex items-center justify-between mx-auto bg-dark"
    >
        <WawyTitle 
            :title="title" 
        />

        <nav class="space-x-4 flex items-end">
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
    }
}
</script>
