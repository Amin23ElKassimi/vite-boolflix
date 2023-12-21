<!-- HTML -->
<template lang="">
    <main>
        <!-- <CardList/> -->
        Lista Film da stampare come Cards
        <article>

        </article>
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