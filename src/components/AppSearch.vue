

<template lang="">
    <div class="mb-2">
        <nav class="navbar bg-body-tertiary">
            <div class="container-fluid">
                <a class="navbar-brand">Netflix</a>
                <form class="d-flex" role="search">
                    <input v-model="searchMovie" class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                    <!-- con la emmit mando evoco la funzione che aggiorna il nome del film e gli mando il nome del film -->
                    <button @click="$emit('searchFilm',searchMovie)" class="btn btn-outline-success" >Search</button>
                </form>
            </div>
        </nav>
    </div>
</template>


<script>



    export default {

        data() {
            return {
                searchMovie: '',
                
            }
        },

        
    }      


</script>



<style lang="">
    
</style>






