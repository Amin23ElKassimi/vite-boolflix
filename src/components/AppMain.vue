<!-- HTML & VUE3 -->
<template lang="">
    <main>
        <!-- Section 01 -->
        <section id="bg-teentitans">
            <img src="../assets/img/jumbotron.jpg" alt="">
            <div id="current-series-button">
                <a href="#">CURRENT SERIES</a>
            </div>
        </section>
        <!-- Section 01 -->
        <section >
            <!-- Serie -->
            <div class="container">
                <AppListSeries/>
            </div>
            <div id="load-more-btn">
                <a href="#">LOAD MORE</a>
            </div>
        </section>
         <!-- Section 02 -->
         <section class="cards">
            <div class="container"> 

                <div class="bonuscard d-flex align-items-center" >
                    <div>
                        <img src="../assets/img/buy-comics-digital-comics.png" class="card-img-top" alt="...">
                    </div>
                    <p>DIGITAL COMICS</p>
                </div>
                <div class="bonuscard d-flex align-items-center" >
                    <div>
                        <img src="../assets/img/buy-comics-merchandise.png" class="card-img-top" alt="...">
                    </div>
                    <p>DIGITAL COMICS</p>
                </div>
                <div class="bonuscard d-flex align-items-center" >
                    <div>
                        <img src="../assets/img/buy-comics-subscriptions.png" class="card-img-top" alt="...">
                    </div>
                    <p>DIGITAL COMICS</p>
                </div>
                <div class="bonuscard d-flex align-items-center" >
                    <div>
                        <img src="../assets/img/buy-comics-shop-locator.png" class="card-img-top" alt="...">
                    </div>
                    <p>DIGITAL COMICS</p>
                </div>
                <div class="bonuscard d-flex align-items-center" >
                    <div>
                        <img src="../assets/img/buy-dc-power-visabuy-comics-digital-comics.png" class="card-img-top" alt="...">
                    </div>
                    <p>DIGITAL COMICS</p>
                </div>
                

            </div>
         </section>
    </main>
</template>

<!-- JavaScript -->
<script>

// Import Del figlio
import AppListSeries from './AppListSeries.vue';

export default {

    name: 'AppMain',

    // Dichiarare componet
    components: {
        AppListSeries
    }
    
}
</script>

<!-- Sass -->
<style lang="scss" scoped>

    // Use StyleSheets
    @use '../scss/partials/variables' as *;
    @use '../scss/partials/mixins' as *;

    main{
        background-color: $main-color;
        color: white;
        position: relative;
    }

    #bg-teentitans {
        width: 100%;
        object-fit: cover;
        img{
            height: 500px;
            width: 100%;
        }
    }

    section {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .container {
        width: 80%;
        margin: 0 auto;
        padding: 4rem 0;
        border-radius: 20px; 
        @include flex(row, center, stretch);
        margin: 0 auto;
        flex-wrap: wrap;
    }
    .cards{
        background-color: #0282f9;
        img{
            width: 100px;
            height: 100px;
            object-fit: contain;
        }
    }

    #current-series-button{
        background-color: #0282f9;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-size: 2rem;
        width: 270px;
        text-align: center;
        position: absolute;
        top: 483px;
        left: 150px;
        a{
            text-decoration: none;
            color: white;
        }
    }

    #load-more-btn{
        background-color: #0282f9;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        font-size: 1.5rem;
        width: 250px;
        text-align: center;
        margin: 2rem;
        padding: 1rem;
        a{
            text-decoration: none;
            color: white;
        }
    }

    h1{
        padding: 3rem 0;
    }


    .bonuscard{
        width: calc(100% / 5);
    }
 
</style>