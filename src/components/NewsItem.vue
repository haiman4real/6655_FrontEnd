<template>
    <div class="newsItem">
        <div style="align-items: center;">
            <img class="imgFile" :src="newsItem.urlToImage">
        </div>
        
        <a :href="newsItem.url">
            <h2>{{ newsItem.title }}</h2>
        </a>
        <h6>Author: {{ newsItem.author }} || Date: {{ newsItem.publishedAt }}</h6>
        <h5>{{ newsItem.description }}</h5>
        
        <!-- <h4>{{ newsItem.content }}</h4> -->
        <p>&nbsp;</p>
        

        <a :href="newsItem.url">
            <button class="newsbtn">Read News...</button>
        </a>
    </div>
    
</template>

<script>
    export default{
        name: 'NewsItem',
        props:{
            newsItem: Array
        }        
    }
</script>

<style scoped>
    div{
        background-color: #ebebeb;
        padding: 1em;
        color: black;
        margin: 5px;
    }
    a{
        text-decoration: none;
    }
    h2{
        color:blueviolet;
    }
    h5{
        font-style: italic;
    }
    h6{
        color: red;
    }
    h4{
        margin: 2px;
    }
    .red{
        background-color: rgb(186, 186, 186);
    }

    .green{
        color: white;
    }

    .imgFile{
        width:auto;
        height: 200px;
    }

    .newsbtn{
        background-color: #4CAF50; /* Green */
        border: none;
        color: white;
        padding: 12px 20px;
        text-align: center;
        text-decoration: none;
        display: inline-block;
        font-size: 10px;
    }
/* 
    @media only screen and (max-width: 500px) {
        div{
            background-color: #ffb89e;
            color: black;
            margin: 2px;
        }
    } */

</style>