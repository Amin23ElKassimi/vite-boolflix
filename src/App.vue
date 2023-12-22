

<!-- HTML -->
<template lang="">
    <AppHeader @searchFilm="getFilms"/>
    <span class="flag-icon flag-icon-AF">Afghanistan</span>
                    <span class="flag-icon flag-icon-gr flag-icon-squared"></span>
    <AppMain :cardList="filmList"/>
    <testFlags/>
</template>

<!-- JavaScript -->
<script>
// Import componentti e libreria Axios
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import testFlags from './components/testFlags.vue';

export default {

    // Dichiarare i componenti importati
    components :{
      AppHeader,
      AppMain, 
      testFlags,

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
                    console.log(response.data.results);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                });
            console.log(name); 
        },

        fetchLanguageFlag() {

        const selectedLanguage = this.selectedLanguage;
        if (this.languageToCountryFlag[selectedLanguage]) {
        this.countryFlag = this.languageToCountryFlag[selectedLanguage];
        } else {
        // Gestione del caso in cui la bandiera non è disponibile
        this.countryFlag = 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse3.mm.bing.net%2Fth%3Fid%3DOIP.Frfsz85r7r3U9i6jjkpHWgHaE8%26pid%3DApi&f=1&ipt=ec61c932d55890fc44c24aa6ef6d13d5f7e9e48a7f508680238333f0074235a9&ipo=images';
        }
        },
 
    },

    // Hook dove richiamo le mie funzioni
    created() {

    this.getFilms();
    console.log(this.filmList);
    
    
    }
  
}

</script>


<!-- SASS -->
<style lang="scss">
  @use './styles/general.scss' as *;

</style>