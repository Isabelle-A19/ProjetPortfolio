<script setup>
    import TitreNiveau2 from './TitreNiveau2.vue';

    const parcours = {
        annee1: {
            entreprise: 'Autosil France',
            date: 'Janvier 1999 - Mai 2002',
            title: 'Responsable logistique adjointe',
            comment: "Missions : Animation d'une équipe de 5 à 6 personnes ; Gestion des approvisionnements et de la production ; Gestion des expéditions nationale et internationale ; Gestion du magasin."
        },
        annee2: {
            entreprise: 'STEF Logistique',
            date: 'Oct 2002 - Aout 2003',
            title: 'Gestionnaire en logistique',
            comment: "Missions : Gestion informatique des flux entrant et sortant ; Paramétrage d'un nouveaux logiciel ; Création d'une procédure informatique."
        },
        annee3: {
            entreprise: 'Cabinet experts comptable PICARD',
            date: 'Sept 2003 - Avril 2004',
            title: 'Comptable - Formation de 7 mois',
            comment: "Missions : Comptabilité générale ; Saisie des ventes, des achats et de la trésorerie ; Préparation et déclaration de la TVA."
        },
        annee4: {
            entreprise: 'Viers automobiles - concession HONDA',
            date: 'Depuis Déc 2005',
            title: 'Assistant Commerciale - CDI',
            comment: "Missions : Gestion des stocks véhicules ; Gestion des dossiers de ventes; Facturation et suivi atelier mécanique et carrosserie ; Gestion de la trésorerie et des comptes bancaires."
        },
    }
</script>

<template>
    <div class="experience">
        <div class="experience__title">
            <span class="material-symbols-outlined">work</span><br>
            <TitreNiveau2>Mes expériences professionnelles</TitreNiveau2>
        </div>
    
        <div class="annee">
            <div class="job" v-for="annee in parcours">
                <h3 class="job__title">{{ annee.entreprise }}</h3>
                <h4 class="job__info">{{ annee.title }} <span class="separation">|</span> {{ annee.date }}</h4>
                <p class="job__comment">{{ annee.comment }}</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .experience {
        width: 60%;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin: auto;
    }

    .experience__title {
        text-align: center;
    }

    .material-symbols-outlined {
        font-size: 4em;
    }

    .job__title {
        font-size: 1.25em;
    }

    .job__info {
        font-size: 1.05em;
    }

    .separation {
        font-style: italic;
        color: #A0006D;
    }

    .job__comment {
        text-indent: 2em;
        text-align: justify;
    }

    .annee {
        margin-top: 15px;
        display: flex;
        flex-direction: column-reverse;
        gap: 25px;
    }

    .job {
        padding: 15px;
        background-color: hsl(347, 33%, 92%);
        border-radius: 25px;
        box-shadow: -4px 5px 10px #060640;
    }

    @media screen and (max-width: 480px) {
        .experience {
            width: 85%;
        }
    }
</style>