<template>
    <div>
  
    <div class="showMovies">
    
      <ul>
        <li class="bg-blue-400 w-32 h-64 m-4 p-8" v-for="name in apiData">
          {{ name }}
         </li>
      </ul>
    </div>
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        apiData: [],
      }
    },
    mounted() {
      let movieNames = ['avengers', 'cruella'];
      for (let movieName of movieNames){
        axios
          .get(`http://www.omdbapi.com/?t=${movieName}&apikey=2b1b57fb`)
          .then(response => this.apiData.push(response.data.Title))
          .catch(error => {
              console.log(error)
          })
  
      }
  
    },
    methods: {
  
  
      }
     
  } 
  </script>
  
  <style scoped>
  
  </style>
  