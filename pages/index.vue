<template>
    <div class="flex flex-col space-y-5 md:space-y-10">
        <section class="bg-dark-soft py-20 lg:py-0 lg:h-screen flex flex-col items-center justify-center">
            <div class="px-4 lg:px-0 lg:w-10/12 mx-auto flex flex-col items-center space-y-5">

                <!-- desktop title -->
                <div class="hidden lg:flex flex-col text-left space-y-1">
                    <WawyTitle title="Bonjour !" class="text-orange text-2xl"/>
                    <div class="flex space-x-2 md:space-x-3 lg:space-x-5">
                        <WawyTitle 
                            v-for="word, index in title"
                            :key="index"
                            :title="word" 
                            class="text-orange text-2xl"
                        />
                    </div>
                </div>
                <!-- mobile title -->
                <div class="flex flex-col lg:hidden text-left space-y-1 font-bold text-orange text-2xl text-center">
                    <p>Bonjour !</p>
                    <p>Je m'appelle Emmanuelle WILD !</p>
                </div>
                <p 
                    class="md:text-lg text-orange py-2"
                > 
                    Ravie de vous rencontrer !
                </p>
                <h1 
                    class="text-xl text-center"
                >
                    Développeuse web. PHP / Symfony, Javascript / VueJS.
                </h1>
                <img 
                    src="~/assets/images/wild-emmanuelle.jpg"
                    alt="Photo de WILD Emmanuelle"
                    class="h-32 w-32 md:w-44 md:h-44 rounded-full justify-self-center shadow-lg"
                >
            </div>
        </section>
        <section class="px-4 lg:px-0 lg:w-8/12 mx-auto lg:h-screen flex flex-col justify-center space-y-5 md:space-y-10">
           <h2 class="w-full text-2xl lg:text-3xl border-b-0.5 border-orange text-orange">
                A propos
            </h2>
            <div class="text-sm md:text-base md:leading-loose flex flex-col space-y-1">
                <div>
                    <font-awesome-icon icon="fa-solid fa-seedling" pull="left" size="5x" class="ml-4 mt-4 pb-1"/>
                    <p>
                        J'ai commencé à apprendre le développement web en autodidacte, quand j'étais au collège. 
                        J'ai donc développé en HTML/CSS un petit site statique, où je proposais des images d'avatars à utiliser 
                        sur les forums de JDR sur la solution PHPBB.
                        <br>
                        <i>(Site crée avec Dreaweaver et que j'ai déployé avec le logiciel FTP expert... une autre époque!)</i>
                    </p>
                </div>
                <br>
                <p>
                    Après près de 10 ans dans le secteur de la santé, j'ai décidé de me reconvertir et de faire du développement web mon métier.
                    J'ai effectué un bootcamp orienté <b>PHP / Symfony</b> de 5 mois, 
                    à l'issue duquel j'ai fait un stage de 6 mois chez 
                    <a href="https://tualu.fr/" target="_blank" class="link-turquoise">tualu.fr</a>
                    , une plateforme de jeu autour du livre <b>(stack technique : MySQL, PHP / Symfony, API Platform, VueJS, TailwindCSS)</b>,
                    où j'occupais un poste de développeuse full stack.
                    Par la suite, j'ai effectué une alternance d'1 an dans cette même entreprise, 
                    pour booster mes connaissances en Javascript, et élargir le champ de mes compétences 
                    <b>(NodeJS, Typescript, React, React Native, GraphQL, CI/CD et Docker)</b>.
                </p>
            </div>
        </section>
        <section class="px-4 lg:px-0 lg:w-11/12 mx-auto">
            <div class="md:flex md:space-x-2 space-y-2 md:space-y-0 mx-auto">
                <skill-card 
                    v-for="skill, index in skills"
                    :key="index" 
                    :skill="skill"
                />
            </div>
            <span class="text-sm md:text-base flex justify-end">** Classement par ordre de maîtrise. </span>

        </section>
        <section class="bg-dark-soft py-10 md:py-20 lg:py-0 lg:h-screen flex flex-col justify-center text-center">
            <div class="px-4 lg:px-0 lg:w-11/12 mx-auto space-y-5 lg:space-y-10">
                <h2 class="text-center text-2xl lg:text-3xl text-orange">
                    Projets récents
                </h2>
                <p> 
                    Vous trouvez que ça ne fait pas beaucoup de projet ? Moi aussi ! <br> Aidez-moi à augmenter le nombre de projets !
                </p>
                <div class="md:grid md:grid-cols-2 gap-2 lg:grid-cols-3">
                    <project-card 
                        v-for="project, index in projects" 
                        :key="index" 
                        :name="project.name" 
                        :description="project.description" 
                        :image="project.image" 
                        :link="project.link"
                        :technologies="project.technologies"
                        :color="project.color"
                        :details="project.details"
                    />
                </div>
            </div>
        </section>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
    name: 'IndexPage',
    data() {
        return {
            title: "Je m'appelle Emmanuelle WILD.".match(/\b(\w+\W+)/g),
            projects: [
                {
                    name: "Tualü",
                    description: "Plateforme de jeu autour du livre",
                    image: "logo-tualu.png",
                    link: "https://tualu.fr/",
                    technologies: "MySQL, PHP / Symfony, Javascript / VueJS, Docker, TailwindCSS, API Platform",
                    details: "Pendant mes 1 ans 1/2 chez Tualu (stage + alternance), j'ai occupé un poste de développeuse fullstack. J'ai appris sur le tas API Platform, VueJS et TailwindCSS. J'ai activement participé à la migration du projet de Twig à VueJS avec API Platform et de Bootstrap à TailwindCSS. J'ai également mis en place le système de paiement via la solution Stripe Checkout, et j'ai réalisé divers developpement back-end : quiz anonyme, exposition des ressources à l'API, calcul du niveau de l'utilisateur sur les livres...",
                    color: "#1e83a3"
                },
                {
                    name: "Wild[e].dev",
                    description: "Mon portfolio",
                    image: "logo-wild-e.gif",
                    link: "https://github.com/wild-e/wild-e.github.io",
                    technologies: "NuxtJS, TailwindCSS, Github actions, Github Pages",
                    details: "Mon portfolio est un projet que j'ai réalisé avec NuxtJS, une techno que j'avais envie d'essayer depuis un moment. J'y ai mis en place un système de CD avec Github Actions, pour déployer automatiquement le site sur Github Pages. Effectivement, utiliser Nuxt pour créer un tout petit site statique est clairement du 'sur-développement', mais j'espère que cela me sera utile pour mes futurs projets.",
                    color: "#ffa500"
                },
                {
                    name: "Excel'Ant",
                    description: "Projet fil rouge de l'alternance",
                    image: "logo-excelant.png",
                    link: "https://github.com/wild-e/2109-wns-remote2-excelant",
                    technologies: "NodeJS, Typescript, React, React Native, GraphQL, Docker, Jest",
                    details: "Excel'Ant est un projet fil rouge de l'alternance réalisé en équipe de 4. Il s'agit d'une application web et mobile de gestion de projet, qui permet de créer des projets, des tâches, des utilisateurs, et de les assigner. Nous avons travaillé avec la méthode Agile, en occupant chacun notre tour les rôles de Product Owner, Scrum Master et développeur. J'ai travaillé à la fois sur le front (React et react Native) que sur le back (Node, GraphQL).",
                    color: "#7D80DA"
                }
            ],
            skills: [
                {
                    title: "Développeuse front-end",
                    icon: "fa-layer-group",
                    list: [
                        "HTML",
                        "CSS",
                        "VueJS 2",
                        "TailwindCSS",
                        "Javascript vanilla",
                        "React",
                        "Typescript",
                        "Nuxt",
                        "React Native",
                    ], 
                },
                {
                    title: "Développeuse back-end",
                    icon: "fa-database",
                    list: [
                        "PHP 7.4",
                        "Symfony 4.4",
                        "API Platform",
                        "MySQL",
                        "Typescript",
                        "NodeJS",
                        "GraphQL",
                    ], 
                },
                {
                    title: "DevOps et théories",
                    icon: "fa-terminal",
                    list: [
                        "POO",
                        "Méthode Agile",
                        "API REST",
                        "Git / Github Actions",
                        "Docker",
                        "CI/CD",
                        "Jest",
                    ], 
                },
            ],
        }
    }
})
</script>
