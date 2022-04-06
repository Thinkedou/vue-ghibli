<template>
    <table class="styled-table">
      <thead>
          <tr>
              <th>Id</th>
              <th>Name</th>
              <th>Year</th>
              <th>Voir</th>
          </tr>
      </thead>
      <tbody>
          <tr v-for="movie in movies" :key="movie.id" >
              <td>{{movie.id}}</td>
              <td>{{movie.title}}</td>
              <td>{{movie.release_date}}</td>
              <td @click="goToMoviesDetails(movie.id)">👀</td>
          </tr>

          <!-- and so on... -->
      </tbody>
  </table>
</template>

<script>
import axios from 'axios'

export default {
  name: 'FilmsList',
  data:()=>({
      movies:[],
  }),
  methods:{
      goToMoviesDetails(moviesId){
          console.log(moviesId)
          this.$router.push({name:'filmsDetails',params:{filmId:moviesId}})
      }
  },
  async created(){

      const movies = await axios.get("https://ghibliapi.herokuapp.com/films")
      this.movies  = movies.data

      console.log('CREATED')
  }
}
</script>






<style scoped>
.styled-table {
    border-collapse: collapse;
    margin: 25px 0;
    font-size: 0.9em;
    font-family: sans-serif;
    min-width: 1200px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.15);
}
.styled-table thead tr {
    background-color: #009879;
    color: #ffffff;

}
.styled-table th,
.styled-table td {
    padding: 12px 15px;
}
.styled-table tbody tr {
    border-bottom: 1px solid #dddddd;
}

.styled-table tbody tr:nth-of-type(even) {
    background-color: #f3f3f3;
}

.styled-table tbody tr:last-of-type {
    border-bottom: 2px solid #009879;
}

.styled-table tbody tr.active-row {
    font-weight: bold;
    color: #009879;
}




</style>
