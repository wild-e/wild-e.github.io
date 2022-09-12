<template>
    <div 
        class="h-64 w-96 flex items-center px-5 rounded-lg shadow-lg transform transition ease-in-out duration-700 hover:scale-110"
        :class="color && `bg-${color}`"
        @mouseenter="hover = true"
        @mouseleave="hover = false"
    >
        <Transition mode="out-in">
            <div 
                v-if="hover"
                :key="2"
                class="justify-evenly flex flex-col h-full text-white"
            >
                <img
                    class="w-1/2 mx-auto font-bold"
                    :src="getUrl()" 
                    :alt="`Projet ${name}`" 
                >
                <p class="text-sm">
                    {{ description }}
                </p>
                <a 
                    :href="link"
                    class="bg-white p-2 shadow-lg font-bold rounded-lg text-center border-b-2 border-l-2 border-greyish hover:text-greyish"
                    :class="color && `text-${color}`"
                    target="_blank"
                >
                    Voir le projet
                </a>
                <div class="border-t pt-2 text-xs text-left">
                    <p class="font-black">Stack technique :</p>
                    <p>
                        {{ technologies }}
                    </p>
                </div>
            </div>
            <img 
                v-else
                :key="1"
                :src="getUrl()" 
                :alt="`Projet ${name}`" 
            >
        </Transition>
    </div>
</template>

<script>
export default {
    name: "ProjectCard",
    props: {
        name: {
            type: String,
            required: true
        },
        description: {
            type: String,
            required: true
        },
        image: {
            type: String,
            required: true
        },
        link: {
            type: String,
            required: true
        },
        technologies: {
            type: String,
            required: true
        },
        color: {
            type: String,
            required: true,
        }
    },
    data() {
        return {
            hover: false
        }
    },
    methods: {
        getUrl()  {
            return require(`~/assets/images/${this.image}`);
        }
    }
}
</script>

<style>
.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

</style>