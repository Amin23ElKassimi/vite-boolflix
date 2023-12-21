
<template lang="">
    <header >
        <nav class="navbar bg-body-tertiary">
            <div class="container-fluid">
                <a class="navbar-brand">Netflix</a>
                <form class="d-flex" role="search">
                    <input v-model="stringSearch" class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                    <!-- con la emmit mando evoco la funzione che aggiorna il nome del film e gli mando il nome del film -->
                    <button @click="$emit('searchFilm',stringSearch)"  >Search</button>
                </form>
            </div>
        </nav>
    </header>
</template>

<script>
export default {




    data() {
        return {
            stringSearch:'',
            
        }
    },
    
}
</script>


<style lang="scss">

    img{
        height: 40px;
    }
    
</style>