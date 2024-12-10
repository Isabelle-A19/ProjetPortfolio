<script setup>
    import { ref } from 'vue'


    import TitreNiveau2 from './TitreNiveau2.vue';
    import Courses from '@/components/Courses.vue';
    import Experiences from '@/components/Experiences.vue';
    import Skills from '@/components/Skills.vue';

    
  const presentationFilter = ref( 'courses' )
</script>

<template>
    <div id="about">
        <div class="presentation">
            <img src="@/assets/images/Audar-logo.png" alt="Audar Logo">
            <div class="presentation__text">
                <TitreNiveau2>Présentation</TitreNiveau2>
                <p>Je suis Isabelle Audar, débutante dans le domaine du web. <br> Actuellement assistante commerciale mais aussi en formation pour développer mes compétences de développeur WEB. <br>
                    Je suis très motivé à enrichir mes connaissances dans ce dommaine et cela dans le but dans faire mon futur métier. <br>
                    Malgré mon expérience récente, j'ai déjà acquis des compétences en HTML, CSS, JavaScript et j'ai déjà réalisé plusieurs projets qui me permettent de mettre en avant mes capacités. <br>
                    Dans ce portfolio, vous découvrirez quelques exemples de mes réalisations, qui illustrent ma passion pour le développement web et mon aptitude à apprendre rapidement. <br>
                    Je suis impatiente de discuter de vos besoins et de découvrir comment je peux vous aider à concrétiser vos projets web. N'hésitez pas à me contacter pour toute question ou pour en savoir plus sur mes réalisations.</p>
                <router-link class="CTA" :to="{hash:'#contact'}">Me contacter</router-link>
            </div>
            <img src="@/assets/images/photoProfil.jpg" alt="Photo d'Isabelle">
            
            
        </div>
    
        <div class="about__filter">
            <button class="about__filter__button CTA" @click="presentationFilter='courses'">Parcours</button>
            <button class="about__filter__button CTA" @click="presentationFilter='experiences'">Expériences</button>
            <button class="about__filter__button CTA" @click="presentationFilter='skills'">Compétences</button>  
        </div>
    
        <div class="about__content">
            <Courses v-if="presentationFilter === 'courses' "/>
        
            <Experiences v-if="presentationFilter === 'experiences' "/>
        
            <Skills v-if="presentationFilter === 'skills' "/>
        </div>
    </div>
</template>

<style scoped>
    .presentation {
        background-color: #dfc1d8;
        display: flex;
        padding: 10px 10%;
        gap : 20px;
        align-items: center;
    }

    .presentation__text {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 15px;
    }

    .presentation__text p {
        width: 60%;
        text-align: justify;
        text-indent: 5%;
    }

    img {
        width: 25%;
        height: 25%;
        border-radius: 20%;
        box-shadow: -4px 5px 25px #060640;
    }

    .about__filter {
        display: flex;
        gap: 15px;
        margin: 15px 0;
        justify-content: center;
    }

    .about__content {
        margin-bottom: 15px;
        margin-bottom: 2em;
    }

    @media screen and (max-width: 480px) {
        .presentation {
            flex-direction: column-reverse;
            padding: 10px 0;
        }
        .presentation__text p {
            width: 85%;
        }
        img {
            width: 50%;
        }
    }
</style>