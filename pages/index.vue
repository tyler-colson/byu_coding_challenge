<template>
  <div>
    <h1>Movie Search Application</h1>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-gH2yIJqKdNHPEq0n4Mqa/HGKIhSkIHeL5AyhkYV8i59U5AR6csBvApHHNl/vI1Bx" crossorigin="anonymous">
    <form action="">
      <input type="text"  name="movieNames" id="movieNames" placeholder="Search Movies...">
      <input type="submit" v-on="value">
    </form>
    <br><br>
    <div class="allMovies container">
      <div class="row"> 
      <Movie
        v-for="movie in movies"
        :key="movie.title" 
        :imovie="movie" 
      />
      </div>
    </div>
  </div>
</template>

<style>
  .allMovies{
    display:flex;
    flex-wrap: wrap;
  }
  form{
    text-align: center;
    margin-top: 40px;
  }
  h1{
    text-align: center;
    margin-top: 20px;
  }
</style>

<script>
  export default {
      async fetch() {
        console.log(this.movies = await fetch(
          'https://api.themoviedb.org/3/search/movie?api_key=afb6a225f5244a45c57fe0c879ad38a7&language=en-US&query=marvel&page=1&include_adult=false'
        ).then(res => res.json()))
      this.movies = this.movies.results;
      },
    data(){
      return {
        movies: []
      }
    }
  }
</script>
