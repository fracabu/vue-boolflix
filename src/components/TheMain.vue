<template>
    <div>
        <div class="moviesList">
            <ul>
                <li v-for="movie in moviesList" :key="movie.i">
                    {{ movie.original_title }}
                    {{ movie.title }}
                    {{ movie.original_language }}
                    {{ movie.vote_average }}

                </li>
            </ul>
        </div>
        <!-- <div class="seriesList">
            <li v-for=" serie in seriesList" :key="serie.id"></li>
            {{ serie.original_title }}
            {{ serie.title }}
            {{ serie.original_language }}
            {{ serie.vote_average }}
        </div> -->
    </div>
</template>

<script>
export default {
    props: {
        moviesList: Array,
        seriesList: Array
    },
}

</script>

<style lang="scss" scoped>
</style>