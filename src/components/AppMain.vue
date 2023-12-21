<!-- HTML -->
<template lang="">
    <main>
        <!-- Lista Film da stampare come Cards -->
        <div class="cards row">                                                          
            <article v-for="card in cardList" class="p-0 text-uppercase fw-bold">
                <h3>
                    {{card.title}}
                </h3>
                <p>
                    {{card.original_title}}
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

// Use 
@use '../styles/partials/variables.scss' as *;
    
    main {
        background-color: $primary-bg;
        padding: 50px;
    }



    article {
        width: calc(100%  / 5 - 1rem);
        margin-left: .5rem;
        margin-right: .5rem;
        margin-bottom: 1rem;
        background-color: $primary-bg;
    }

    #card-list{
        background-color: white;
    }

    .row{
        color: white;
    }
    
</style>