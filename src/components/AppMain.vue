<!-- HTML -->
<template lang="">
    <main>
        <!-- Lista Film da stampare come Cards -->
        <div class="lista">                                                          
            <article @click="printTest" v-for="card in cardList" class="cards text-uppercase fw-bold">
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

                <p v-if="countryFlag">
                    Bandiera della nazione corrispondente:
                    <img :src="countryFlag" alt="Country Flag" style="width: 30px; height: 20px;">
                </p>

                <p v-else>
                    Bandiera non disponibile per la nazione selezionata.
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

            languageToCountryFlag: {
                    en: '🇺🇸',
                    es: '🇪🇸',
                    // Aggiungi altri mapping lingua-banidera secondo necessità
                    },
            selectedLanguage: 'en',
            countryFlag: null,
            // Mappatura String to IMG
            languageToCountryFlag: {
                    en: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwallpapercave.com%2Fwp%2Fwp4056551.jpg&f=1&nofb=1&ipt=2bf32566178b364560735e2d9debf82e914a0930cac2fa8ceeccbb08887c0c0a&ipo=images',
                    es: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.fF_zQh_qMZdti-_EOVk2dgHaDt%26pid%3DApi&f=1&ipt=ecb07df835c487d405ca9976343c0300169d94a214c11fdcdb50d64e02da2b68&ipo=imagesurl_dell_immagine_bandiera_es',
                    // Aggiungi altri mapping lingua-bandiera secondo necessità
                     },
                      
        }
    },

    methods: {

    fetchLanguageFlag() {

        const selectedLanguage = this.cardList[0].original_language;
        
        if (this.languageToCountryFlag[selectedLanguage]) {
            this.countryFlag = this.languageToCountryFlag[selectedLanguage];
        } else {
            // Gestione del caso in cui la bandiera non è disponibile
            this.countryFlag = 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse3.mm.bing.net%2Fth%3Fid%3DOIP.Frfsz85r7r3U9i6jjkpHWgHaE8%26pid%3DApi&f=1&ipt=ec61c932d55890fc44c24aa6ef6d13d5f7e9e48a7f508680238333f0074235a9&ipo=images';
        }
     },

     printTest() {
        console.log(this.cardList);
     },


    },

    // Props Ricevute da AppVue
    props: {
        cardList : {
            type : Object,
            require: true,
        }

    },

    // Hook dove richiamo le mie funzioni
    created() {


    }



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