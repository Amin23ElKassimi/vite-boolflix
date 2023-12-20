<template lang="">
  <AppHeader/>

</template>

<script>

// Import Dei componenti
import { store } from './js/store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';

export default {

  // Dichiarazione Componenti
  components:{
    AppHeader
  },

  // Data Relativi al componente
  data() {
    return {
      characters: [],
      store
    }
  },

  // Metodi e libreirie funzioni
  methods: {


    getCharacters(){
      axios.get('https://rickandmortyapi.com/api/character')
      .then((response) => {
        // handle success
        console.log(response);
        this.store.charactersList = response.data.results;
      })
      .catch(function (error) {
        // handle error
        console.error(error);
      });
    }
  },

  // Hook che richiama la funzione Azios
  created() {
    this.getCharacters();
  },



}
</script>

<style lang="scss">
  @use './styles/general.scss';

</style>