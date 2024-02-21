<!-- HTML -->
<template lang="">

    <AppHeader @searchFilm="getFilms"/>
    <AppMain :cardList="filmList"/>

</template>

<!-- JavaScript -->
<script>

    // Import componentti e libreria Axios
    import axios from 'axios';
    import AppHeader from './components/AppHeader.vue';
    import AppMain from './components/AppMain.vue';

    export default {

        // Dichiarare i componenti importati
        components :{
        AppHeader,
        AppMain, 

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
            getFilms( name ) {
                //            Qui ho fatto la concatenazione dell'URL
                axios.get(this.apiUrl + name)
                    .then( (response) => {
                        // handle success
                        // console.log(response.data.results);
                        this.filmList = response.data.results;
                        
                    })
                    .catch(function (error) {
                        // handle error
                        console.log(error);
                    });
                
            },
    
        },

        // Hook dove richiamo le mie funzioni
        created() {

        this.getFilms();
        
        
        }
    
    }

</script>


<!-- SASS -->
<style lang="scss">
  @use './styles/general.scss' as *;

</style>