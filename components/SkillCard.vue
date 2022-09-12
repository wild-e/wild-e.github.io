<template>
    <div class="bg-dark-soft shadow-lg rounded-md h-32 w-32 select-none flex flex-col space-y-5 items-center justify-center transform transition ease-in-out duration-700 hover:scale-110">
        <p 
            class="uppercase text-center font-roboto font-bold text-ghost tracking-widest"
        >
            {{ name }}
        </p>
        <div class="flex space-x-2">
            <font-awesome-icon v-for="star, index in stars" :key="index" icon="fa-solid fa-star" beat style="--fa-animation-duration: 5s;" class="text-orange"/>
        </div>
    </div>
</template>

<script>
export default {
    name: "SkillCard",
    props: {
        name: {
            type: String,
            required: true
        },
        stars: {
            type: Number,
            required: true
        }
    }
}
</script>