<template lang="">

  <p>Seleziona una lingua:</p>

  <select v-model="selectedLanguage" @change="fetchLanguageFlag">
    <option value="en">Afghanistam</option>
    <option value="es">Palestine</option>
    <!-- Aggiungi altre opzioni per le lingue che vuoi supportare -->
  </select>

  <p v-if="countryFlag">
    Bandiera della nazione corrispondente:
    <img :src="countryFlag" alt="Country Flag" style="width: 30px; height: 20px;">
  </p>

  <p v-else>
    Bandiera non disponibile per la nazione selezionata.
  </p>

</template>



<script>

export default {
    


  data() {
    return {

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

      const selectedLanguage = this.selectedLanguage;
      if (this.languageToCountryFlag[selectedLanguage]) {
        this.countryFlag = this.languageToCountryFlag[selectedLanguage];
      } else {
        // Gestione del caso in cui la bandiera non è disponibile
        this.countryFlag = 'https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse3.mm.bing.net%2Fth%3Fid%3DOIP.Frfsz85r7r3U9i6jjkpHWgHaE8%26pid%3DApi&f=1&ipt=ec61c932d55890fc44c24aa6ef6d13d5f7e9e48a7f508680238333f0074235a9&ipo=images';
      }
    },

  },

  created() {
    // Chiamata API per ottenere la lingua iniziale o altre operazioni all'avvio dell'app
    this.fetchLanguageFlag();
  },








}
</script>










<style lang="">
    
</style>