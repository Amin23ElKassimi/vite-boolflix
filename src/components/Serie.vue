<!-- HTM & Vue -->
<template lang="">
    <article >
        <img :src="imageSrc" alt="">
        <h4>
            {{ title }}
        </h4>
        <p>
            {{ type }}
        </p>
    </article>
</template>

<!-- JAvaScript -->
<script>

export default {
    name: 'Serie',

    data() {
        return {

        }

    },
    // Dichiarazione Props
    props: {
        title : String,
        type : String,
        imageSrc : {
            type: [String, Boolean],
            required: true
        },
        price : [Number, String],
    }
    
} 
</script>

<!-- Sass -->
<style lang="scss" scoped>

    // Use StyleSheets
    @use '../scss/partials/variables' as *;
    @use '../scss/partials/mixins' as *;

    article{
        width: calc((100% / 6) - 2rem) ;
        margin: 0 1rem;
        text-align: center;


        img{
            width: 100%;
            height: 150px;
        }


    }

    
</style>