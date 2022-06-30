<template>
    <div>
        <div class="moviesList">
            <ul>
                <li v-for="movie in moviesList" :key="movie.id">
                    {{ movie.original_title }}
                    {{ movie.title }}
                    {{ movie.original_language }}
                    {{ movie.vote_average }}
                    <MovieCard :movie="movie"></MovieCard>
                </li>
            </ul>
        </div>
        <div class="seriesList">
            <li v-for="(serie,i) in seriesList" :key="i">
            {{ serie.original_title }}
            {{ serie.title }}
            {{ serie.original_language }}
            {{ serie.vote_average }}
            
            </li>
        </div>
    </div>
</template>

<script>
import MovieCard from "./MovieCard"
export default {
    props: {
        moviesList: Array,
        seriesList: Array
    },  components: {
 
    MovieCard
},
}

</script>

<style lang="scss" scoped>
</style>