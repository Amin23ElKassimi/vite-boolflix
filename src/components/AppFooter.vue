<!-- HTM & Vue -->
<template lang="">
    <footer>

        <!-- Meta  -->
         <section class="meta">
            <div id="container">
                <div>
                    <!-- DC Comics & SHOP -->
                    <div>
                        <nav id="dccomicslinks">
                            <h2>
                                DC COMICS
                            </h2>
                            <ul>
                                <li v-for="(link, index) in dcComicsLinks" >
                                {{ link.content}}
                                </li>
                            </ul>
                        </nav>
                        <nav id="shoplinks">
                            <h2>
                                SHOP
                            </h2>
                            <ul>
                                <li v-for="(link, index) in shopLinks" >
                                {{ link.content}}
                                </li>
                            </ul>
                        </nav>
                    </div>
                    <!-- DC -->
                    <div>
                        <nav id="dclinks">
                            <h2>
                                DC
                            </h2>
                            <ul>
                                <li v-for="(link, index) in dcComicsLinks" >
                                {{ link.content}}
                                </li>
                            </ul>
                        </nav>
                    </div>
                    <!-- Sites -->
                    <div>
                        <nav id="siteslinks">
                            <h2>
                                SITES
                            </h2>
                            <ul>
                                <li v-for="(link, index) in shopLinks" >
                                {{ link.content}}
                                </li>
                            </ul>
                        </nav>
                    </div>
                </div>
            </div>
         </section>

          <!-- Sign Up Now -->
        <section class="content">
            <div id="container">
                <div class="d-flex justify-content-between align-items-center" role="search">
                    <div id="sign-btn" type="submit">SIGN-UP NOM!</div>
                    <div>
                        <div id="follow-info" type="submit">FOLLOW US </div>
                        <img src="../assets/img/footer-facebook.png" alt="" class="m-2">
                        <img src="../assets/img/footer-twitter.png" alt="" class="m-2">
                        <img src="../assets/img/footer-youtube.png" alt="" class="m-2">
                        <img src="../assets/img/footer-pinterest.png" alt="" class="m-2">
                        <img src="../assets/img/footer-periscope.png" alt="" class="m-2">

                    </div>
                </div>
            </div>
         </section>

    </footer>
</template>

<!-- JAvaScript -->
<script>
export default {
    // NAme Application
    name: 'AppFoter',
    // Data
    data() {
        return {
            dcComicsLinks: [
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
                    content: 'videos',
                    url: '#',
                    active: false,
                },
                {
                    content: 'news',
                    url: '#',
                    active: false,
                },
            ],
            shopLinks: [
                {
                    content: 'Shop DC',
                    url: '#',
                    active: false,
                },
                {
                    content: 'Shop DC Collectibles',
                    url: '#',
                    active: false,
                },
            ],
            dcLinks: [
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
            sitesLinks: [
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

    footer{
        background-color: $main-color;
        color: white;
    }

    #container {
        @include my-wrapper();
        @include flex(column,center,start);
        top: 50%;

        >div{
            display: flex;
            width: 100%;
        }
        nav{
            margin: 0 3rem 0 0 ;
        }
    }
    .meta{
        background-image: url(../assets/img/footer-bg.jpg);
        background-position: center;
    }

    h2{
        padding-bottom: 1.5rem;
    }

    ul{
        list-style-type: none;
        padding: 0;
        li{
            margin-bottom: 0.5rem;
        }
    }

    a {
        text-decoration: none;
        color: white;
    }

    #sign-btn{
        border: 2px solid #0282f9;
        text-align: center;
        padding: 1rem;
        font-weight: bold;
    }

    #follow-info{
        color: #0282f9;
        font-weight: bold;
        font-size: 1.5rem;
        display: inline-block;
        margin-right: 1rem;
    }

</style>