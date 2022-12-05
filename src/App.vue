<template>
  <div class="container">
    <img class="mainLogo" alt="Vue logo" src="./assets/news2.png">
    <NewsBox :allNews="allNews"/>
  </div>
</template>

<script>
//s1: import headertop
import NewsBox from './components/NewsBox.vue';

  export default{
        name: 'App',
        components:{
          NewsBox
        },
        data(){
          return {
            allNews: []
          }
        },
        methods:{
          async  fetchNews(){
              const res = await fetch("http://localhost:5512/api")
              // const res = await fetch("https://emmaogunwobi.herokuapp.com/api")
              const data = await res.json()

              console.log(data)

              return data

          },

          
        },
        async created(){
              this.allNews = await this.fetchNews()

          }
        //s2: register the imported component
    }
</script>


<style>
#app {
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 10px;
}

  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body{
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
  }

  .container{
    max-width: 1540px;
    margin: 30px auto;
    overflow:  auto;
    min-height: 300px;
    /* border: 0.3em solid black; */
    padding: 30px;
    border-radius: 5px;
  }

  .mainLogo{
      width:auto;
      height: 200px;
    }

  @media only screen and (max-width:500px) {
    .container{
      max-width: 500px;
      margin: 30px auto;
      overflow:  auto;
      min-height: 300px;
      /* border: 0.3em solid black; */
      padding: 30px;
      border-radius: 5px;
    }

    .mainLogo{
      width:200px;
      height: auto;
    }
  }

</style>