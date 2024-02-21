<!-- HTML & VUE JS -->
<template lang="">
    <main>
        <!-- Lista Film da stampare come Cards -->
        <div class="lista">                                                          
            <article @click="printTest" v-for="(card, index) in cardList"  class="cards text-uppercase fw-bold">
                <!-- Card Title  -->
                <p class="title">
                    {{card.title}}
                </p>
                <!-- Original Title -->
                <p>
                    {{card.original_title}}
                </p>
                <!-- Language -->
                <p>
                    Original Language: {{card.original_language}} 
                    <img :src="'/public/images/lang/' + card.original_language + '.png'" alt="Country Flag" style="width: 30px; height: 20px;">
                </p> 
                <!-- Voto -->
                <p>
                    Vote: {{card.vote_average}}
                </p>    
             </article>
        </div>
    </main>
</template>

<!-- JavaScript -->
<script>

// 
export default {


    // Database variabili 
    data() {
        return {

            selectedLanguage: '',
            countryFlag: null,
            // Mappatura String to IMG
            languageToCountryFlag: {
                    en: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fwallpapercave.com%2Fwp%2Fwp4056551.jpg&f=1&nofb=1&ipt=2bf32566178b364560735e2d9debf82e914a0930cac2fa8ceeccbb08887c0c0a&ipo=images',
                    es: 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse2.mm.bing.net%2Fth%3Fid%3DOIP.fF_zQh_qMZdti-_EOVk2dgHaDt%26pid%3DApi&f=1&ipt=ecb07df835c487d405ca9976343c0300169d94a214c11fdcdb50d64e02da2b68&ipo=imagesurl_dell_immagine_bandiera_es',
                    de:'https://external-content.duckduckgo.com/iu/?u=http%3A%2F%2Fwww.gcpr.net%2Fwp-content%2Fuploads%2F2014%2F04%2FPakistan-Flag.png&f=1&nofb=1&ipt=04cab663a6564f0d5850f26ff0eaac261cba985df8fcbba6be38f4ef13865f50&ipo=images',
                    // Aggiungi altri mapping lingua-bandiera secondo necessità
                     },
                      
        }
    },

    methods: {

    fetchLanguageFlag() {

        const selectedLanguage = this.cardList[1].original_language;
        
        if (this.languageToCountryFlag[selectedLanguage]) {
            this.countryFlag = this.languageToCountryFlag[selectedLanguage];
        }
        
        else {
            // Gestione del caso in cui la bandiera non è disponibile
            this.countryFlag = 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse3.mm.bing.net%2Fth%3Fid%3DOIP.Frfsz85r7r3U9i6jjkpHWgHaE8%26pid%3DApi&f=1&ipt=ec61c932d55890fc44c24aa6ef6d13d5f7e9e48a7f508680238333f0074235a9&ipo=images';
        }
        
     },

     printTest(){
        console.log(this.countryFlag);
     },

     created() {
    // Chiamata API per ottenere la lingua iniziale o altre operazioni all'avvio dell'app
    this.fetchLanguageFlag();
  },



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