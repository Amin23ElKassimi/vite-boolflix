<!-- HTML -->
<template lang="">
    <main>
        <!-- <AppSearch @searchFilm="updateSearchMovie"/> -->
        <input v-model="searchMovie" class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
        <!-- con la emmit mando evoco la funzione che aggiorna il nome del film e gli mando il nome del film -->
        <button @click="updateSearchMovie"   class="btn btn-outline-success" >Search</button>
        <CardList/>
    </main>
</template>

<!-- JavaScript -->
<script>

// Importa Componente
import CardList from './CardList.vue';
import AppSearch from './AppSearch.vue';
import axios from 'axios';

// 
export default {
    //Dichiara Componente 
    components :{
    CardList,
    AppSearch
    },

    // Database variabili 
    data() {
        return {
            filmList: [],
            searchMovie: '',
            apiUrl: `https://api.themoviedb.org/3/search/movie?api_key=f032778f20863c5cc77348fa8099a129&query=`,
            
        }
    },

    // Dove Scrivere le Funzioni
    methods: {
        
        // Metodo Axios
        getfilms() {
            //            Qui ho fatto la concatenazione dell'URL
            axios.get(this.apiUrl + this.searchMovie)
                .then( (response) => {
                    // handle success
                    // console.log(response.data.results);
                    this.filmList = response.data.results;
                    console.log(response.data.results);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
        },
        
        

        updateSearchMovie() {
        
            console.log(this.searchMovie);
            this.getfilms();

        }
    },

      // Hook dove richiamo le mie funzioni
      created() {

      this.getfilms();

      
      }

    



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