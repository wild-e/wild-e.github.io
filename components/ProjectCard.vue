<template>
    <div 
        class="flex items-center justify-evenly h-full py-4 px-3 md:p-5 rounded-lg shadow-lg transform transition ease-in-out duration-700 hover:scale-105"
        :style="`background-color: ${color}`"
    >
        <div 
            class="justify-evenly flex flex-col h-full text-white space-y-4"
        >
            <img
                class="w-1/2 mx-auto font-bold"
                :src="getUrl()" 
                :alt="`Projet ${name}`" 
            >
            <p class="text-sm">
                {{ description }}
            </p>
            <details class="cursor-pointer inline">
                <summary 
                    class="text-sm md:text-base list-none bg-white p-2 shadow-lg font-bold rounded-lg text-center border-b-2 border-l-2 border-greyish hover:text-greyish"
                    :style="`color: ${color}`"
                >
                    En savoir plus sur mon travail
                    <font-awesome-icon icon="fa-solid fa-magnifying-glass-plus" />
                </summary>
                <p 
                    class="text-sm mt-5"
                >
                    {{ details }}
                </p>
            </details>
            <a 
                :href="link"
                class="bg-white p-2 shadow-lg font-bold rounded-lg text-center border-b-2 border-l-2 border-greyish hover:text-greyish"
                :style="`color: ${color}`"
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
        details: {
            type: String,
            required: true,
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
    /* details[open] summary ~ * {
    animation: sweep 0.5s ease-in-out;
    }
    @keyframes sweep {
        0%    {opacity: 0; margin-top: -10px}
        100%  {opacity: 1; margin-top: 0px}
    } */
</style>