<template>
    <div class="movie col-4">
        <div><b>Title: {{imovie.original_title}}</b></div>
        <div>Popularity Score: {{imovie.popularity}}</div>
        <img 
            :src="'http://image.tmdb.org/t/p/w185'+imovie.poster_path"
            :alt="imovie.title"
        />
    </div>
</template>

<style>
.movie{
    margin-bottom:30px;
    text-align: center;

}
</style>

<script>
export default {
    props: {
        imovie: {
            default: () => {}
        }
    }
}
</script>
