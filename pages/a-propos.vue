<template>
    <div class="flex flex-col space-y-10">
        <section class="bg-dark-soft h-screen flex flex-col items-center justify-center">
            <div class="w-10/12 mx-auto flex flex-col items-center space-y-5">
                <div class="text-left space-y-1">
                    <WawyTitle title="Bonjour !" class="text-orange"/>
                    <div class="flex space-x-5">
                        <WawyTitle 
                            v-for="word, index in title"
                            :key="index"
                            :title="word" class="text-orange"
                        />
                    </div>
                </div>

                <p class="text-lg text-orange py-2"> Ravie de vous rencontrer !</p>
                <h1 class="text-xl">Développeuse web. PHP / Symfony, Javascript / VueJS.</h1>
                <img src="~/assets/images/wild-emmanuelle.jpg" alt="Photo de WILD Emmanuelle" class="w-44 h-44 rounded-full justify-self-center shadow-lg">
            </div>
        </section>
        <section class="w-8/12 mx-auto h-screen flex flex-col justify-center space-y-10">
           <h2 class="w-full text-3xl border-b-0.5 border-orange text-orange">
                A propos
            </h2>
            <div class="leading-loose flex flex-col space-y-1">
                <div>
                    <font-awesome-icon icon="fa-solid fa-seedling" pull="left" size="6x" class="ml-4 mt-4 pb-1"/>
                    <p>
                        J'ai commencé à apprendre le développement web en autodidacte, quand j'étais au collège. 
                        J'ai donc développé en HTML/CSS un petit site statique, où je proposais des images d'avatars à utiliser 
                        sur les forums de JDR sur la solution PHPBB.
                        <br>
                        <i>(Site crée avec Dreaweaver et que j'ai déployé avec le logiciel FTP expert... une autre époque!)</i>
                        <br>
                        Ensuite, mon niveau moyen en math m'a fait me tourner vers le milieu de la santé. 
                    </p>
                </div>
                <br>
                <p>
                    Après près de 10 ans dans le secteur du soin, j'ai décidé de me reconvertir et de faire du développement web mon métier.
                    J'ai effectué un bootcamp <i>PHP / Symfony</i> de 5 mois, 
                    à l'issue duquel j'ai fait un stage de 6 mois chez 
                    <a href="https://tualu.fr/" target="_blank" class="link-turquoise">tualu.fr</a>
                    , une plateforme de jeu autour du livre.
                    Par la suite, j'ai effectué une alternance d'1 an dans cette même entreprise, 
                    pour booster mes connaissances en Javascript, et élargir le champ de mes compétences 
                    <i>(NodeJS, Typescript, React, GraphQL et Docker)</i>.
                </p>
            </div>
        </section>
        <section class="w-11/12 flex space-x-2 mx-auto">
            <div class="w-full border border-greyish rounded-xl p-5">
                <div class="flex flex-col space-y-4 justify-center items-center">
                    <font-awesome-layers class="fa-4x" fixed-width>
                        <font-awesome-icon icon="fa-solid fa-circle" />
                        <font-awesome-icon icon="fa-solid fa-database" transform="shrink-6" class="text-dark" />
                    </font-awesome-layers>
                    <h2 class="text-center text-orange">
                        Développeuse back-end
                    </h2>
                    <div class="grid grid-cols-2 gap-4">
                        <skill-card 
                            v-for="skill, index in skillsBackend" 
                            :key="index" 
                            :name="skill.name" 
                            :stars="skill.stars"
                        />
                    </div>
                </div>
            </div>
            <div class="w-full border border-greyish rounded-xl p-5">
                <div class="flex flex-col space-y-4 justify-center items-center">
                    <font-awesome-layers class="fa-4x" fixed-width >
                        <font-awesome-icon icon="fa-solid fa-circle" />
                        <font-awesome-icon icon="fa-solid fa-layer-group" transform="shrink-5" class="text-dark" />
                    </font-awesome-layers>
                    <h2 class="text-center text-orange">
                        Développeuse front-end
                    </h2>
                    <div class="grid grid-cols-2 gap-4">
                        <skill-card 
                            v-for="skill, index in skillsFrontend" 
                            :key="index" 
                            :name="skill.name" 
                            :stars="skill.stars"
                        />
                    </div>
                </div>
            </div>
            <div class="w-full border border-greyish rounded-xl p-5">
                <div class="flex flex-col space-y-4 justify-center items-center">
                    <font-awesome-layers class="fa-4x" fixed-width>
                        <font-awesome-icon icon="fa-solid fa-circle" />
                        <font-awesome-icon icon="fa-solid fa-terminal" transform="shrink-8" class="text-dark" />
                    </font-awesome-layers>
                    <h2 class="text-center text-orange">
                        Notions de devOps
                    </h2>
                    <div class="grid grid-cols-2 gap-4">
                        <skill-card 
                            v-for="skill, index in skillsDevops" 
                            :key="index" 
                            :name="skill.name" 
                            :stars="skill.stars"
                        />
                    </div>
                </div>
            </div>
        </section>
        <section class="bg-dark-soft h-screen flex flex-col justify-center text-center">
            <div class="w-11/12 mx-auto space-y-10">
                <h2 class="text-center text-3xl text-orange">
                    Projets récents
                </h2>
                <p> Vous trouvez que ça ne fait pas beaucoup de projet ? Moi aussi ! <br> Aidez-moi à augmenter le nombre de projets !</p>
                <div class="flex justify-evenly">
                    <project-card 
                        v-for="project, index in projects" 
                        :key="index" 
                        :name="project.name" 
                        :description="project.description" 
                        :image="project.image" 
                        :link="project.link"
                        :technologies="project.technologies"
                        :color="project.color"
                    />
                </div>
            </div>
        </section>
    </div>
</template>

<script>
    export default {
        name: "AboutPage",
        data() {
            return {
                title: "Je m'appelle Emmanuelle WILD.".match(/\b(\w+\W+)/g),
                projects: [
                    {
                        name: "Tualü",
                        description: "Plateforme de jeu autour du livre. J'ai travaillé sur le projet pendant 1 an et demi en tant que développeuse full-stack.",
                        image: "logo-tualu.png",
                        link: "https://tualu.fr/",
                        technologies: "MySQL, PHP / Symfony, Javascript / VueJS, Docker, TailwindCSS, API Platform",
                        color: "tualu-blue"
                    },
                    {
                        name: "Wild[e].dev",
                        description: "Mon portfolio développé avec NuxtJS, une techno que je ne connaissais pas encore.",
                        image: "logo-wild-e.gif",
                        link: "https://github.com/wild-e/wild-e.github.io",
                        technologies: "NuxtJS, TailwindCSS, Github actions, Github Pages",
                        color: "orange"
                    }
                ],
                skillsBackend: [
                    {
                        name: "PHP 7.4",
                        stars: 2
                    },
                    {
                        name: "Symfony 4.4",
                        stars: 2
                    },
                    {
                        name: "NodeJS",
                        stars: 1
                    },
                    {
                        name: "MySQL",
                        stars: 2
                    },
                    {
                        name: "API Platform",
                        stars: 2
                    },
                    {
                        name: "GraphQL",
                        stars: 1
                    },
                ],
                skillsFrontend: [
                    {
                        name: "HTML",
                        stars: 3
                    },
                    {
                        name: "CSS",
                        stars: 2
                    },
                    {
                        name: "Javascript",
                        stars: 2
                    },
                    {
                        name: "VueJS 2",
                        stars: 2
                    },
                    {
                        name: "NuxtJS",
                        stars: 1
                    },
                    {
                        name: "React",
                        stars: 1
                    },
                    {
                        name: "Tailwind",
                        stars: 3
                    },
                ],
                skillsDevops: [
                    {
                        name: "Docker",
                        stars: 1
                    },
                    {
                        name: "Git / Github",
                        stars: 2
                    },
                    {
                        name: "Jest",
                        stars: 1
                    },
                ]
            }
        }
    }
</script>