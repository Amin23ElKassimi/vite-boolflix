

<!-- HTML -->
<template lang="">
    <AppHeader/>
    <AppMain/>
</template>

<!-- JavaScript -->
<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  // DDichiarare i componenti importati
  components :{
    AppHeader,
    AppMain

  },


  
}

</script>


<!-- SASS -->
<style lang="scss">
  @use './styles/general.scss' as *;

</style>