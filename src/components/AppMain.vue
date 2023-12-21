<!-- HTML -->
<template lang="">
    <main>
        <!-- Lista Film da stampare come Cards -->
        <div class="lista">                                                          
            <article v-for="card in cardList" class="cards text-uppercase fw-bold">
                <p class="title">
                    {{card.title}}
                </p>
                <p>
                    {{card.original_title}}
                </p>
                <p>
                    Original Language: {{card.original_language}} {{en}}
                </p>
                <p>
                    Vote: {{card.vote_average}}
                </p>
             </article>
        </div>
    </main>
</template>

<!-- JavaScript -->
<script>

// Importa Componente


// 
export default {


    // Database variabili 
    data() {
        return {
            filmList: [],
            languageToCountryFlag: {
                    en: '🇺🇸',
                    es: '🇪🇸',
                    // Aggiungi altri mapping lingua-banidera secondo necessità
                    },
                      
        }
    },

    // Props Ricevute da AppVue
    props: {
        cardList : {
            type : Object,
            require: true,
        }

    },




}
</script>

<!-- SCSS -->
<style lang="scss">


@use '../styles/partials/variables.scss' as *;
    
    main {
        background-color: $primary-bg;
        padding: 50px;
    }

    .lista{
        display: flex;
        flex-wrap: wrap;
    }

    .cards{
        color: white;
        width: calc(100% / 5 - 1rem);
        padding: .5rem;
        margin-left: .5rem;
        margin-right: .5rem;
        margin-bottom: 1rem;
        background-color: $primary-bg;
        background-color: #521c76;
        text-align: center;
    }

    .title{
        color: yellow;
    }

    
</style>