<template>
    
    <div class="blogGrid">
        <div class="blogContent" v-for= "news in allNews" :key="news.id">
            <NewsItem :newsItem="news"/>
        </div>
    </div>
    
   
</template>

<script>
import NewsItem from './NewsItem.vue';
    export default{
        name: 'NewsBox',
        components:{
            NewsItem
        },
        props:{
            allNews: Array
        }
    }
</script>

<style scoped>
    .bookbox{
        background-color: bisque;
        padding: 1em;
        color: gray;
    }

    .blogGrid {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        grid-gap: 10px;
    }



    .blogContent h2{
        margin-bottom: -20px;
    }

    .blogContent h5{
        margin-bottom: -10px;
    }



    .blogContent a{
        color: var(--white);
        text-decoration: none;
        text-transform: capitalize;
    }

    .blogContent a:hover{
        transform: scale(1.2);
        transition: 0.3s;
    }

    @media only screen and (max-width:500px) {
        .blogGrid {
            display: grid;
            grid-template-columns: 1fr;
            grid-gap: 10px;
        }
    }

</style>