<!-- HTML & VUE JS -->
<template lang="">
    <header >
        <nav class="navbar bg-body-tertiary">
            <div class="container-fluid">
                <a class="navbar-brand">Netflix</a>
                <div class="d-flex" role="search">
                    <input v-model="stringSearch" class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                    <!-- con la emmit mando evoco la funzione che aggiorna il nome del film e gli mando il nome del film -->
                    <button @click="$emit('searchFilm', stringSearch);" class="btn btn-primary">Search</button> <!-- npmprevent  usato per mandare il dato prima che avvenga la ricarica della pagina perche qui uso il form--> 
                </div>
            </div>
        </nav>
    </header>
</template>

<!-- JavaScript -->
<script>

export default {

    data() {
        return {
            stringSearch:'',
            
        }
    },

    methods: {
        log(stringa){
            alert(stringa);
        }
    },
    
}
</script>

<!-- SCSS -->
<style lang="scss">

    img{
        height: 40px;
    }
    
</style>


