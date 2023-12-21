<!-- HTML -->
<template lang="">
    <main>
        <!-- <CardList/> -->
        <!-- Lista Film da stampare come Cards -->
        <div class="cards row">                                 <!--Prop  -->                               
            <article class="p-0 text-uppercase fw-bold">
                <section class="image">
                    <img :src="card.card_images[0].image_url" alt="">
                </section>
                <h3>
                    {{card.name}}
                </h3>
                <p>
                    {{card.archetype}}
                </p>
             </article>
        </div>
    </main>
</template>

<!-- JavaScript -->
<script>

// Importa Componente
import CardList from './CardList.vue';

import axios from 'axios';

// 
export default {

    //Dichiara Componente 
    components :{
    CardList,
    },

    // Database variabili 
    data() {
        return {
            filmList: [],          
        }
    },

    // Dove Scrivere le Funzioni
    methods: {
        

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
    
</style>