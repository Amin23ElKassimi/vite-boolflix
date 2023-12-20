<!-- HTM & Vue -->
<template lang="">
    <header>
        <div id="container">
            <section class="logo">
                <img src="../assets/img/dc-logo.png" alt="">
            </section>
            <nav >
                <ul class="m-0">
                    <li v-for="(link, index) in navLinks" >
                    {{ link.content}}
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<!-- JAvaScript -->
<script>
export default {
    name: 'AppHeader',
    data() {
        return {
            navLinks: [
                {
                    content: 'charters',
                    url: '#',
                    active: false,
                },
                {
                    content: 'comics',
                    url: '#',
                    active: false,
                },
                {
                    content: 'movies',
                    url: '#',
                    active: false,
                },
                {
                    content: 'tv',
                    url: '#',
                    active: false,
                },
                {
                    content: 'games',
                    url: '#',
                    active: false,
                },
                {
                    content: 'collectibles',
                    url: '#',
                    active: false,
                },
                {
                    content: 'videos',
                    url: '#',
                    active: false,
                },
                {
                    content: 'fans',
                    url: '#',
                    active: false,
                },
                {
                    content: 'news',
                    url: '#',
                    active: false,
                },
                {
                    content: 'shop',
                    url: '#',
                    active: false,
                },
            ],
        }
    },
    
} 
</script>

<!-- Sass -->
<style lang="scss" scoped>

    // Use StyleSheets
    @use '../scss/partials/variables' as *;
    @use '../scss/partials/mixins' as *;


    #container {
        width: 80%;
        margin: 0 auto;
        margin: 0 1rem;
        @include flex(row,space-between,center);
    }

    .logo img{
        height: 80px;
    }

    ul {
        @include flex(row,space-between,center);
        list-style-type:none ;
    }

    li{
        font-size: 1.2rem;
        padding: 3rem 1rem;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        text-transform: uppercase;
        &:hover{
            color: #0282f9;
            border-bottom: 5px solid #0282f9;
        }
        
    }
    
</style>