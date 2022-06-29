<template>
    <div>
        <div class="moviesList">
            <ul>
                <li v-for = "movie in moviesList" :key="movie.id">
                {{movie.original_title}}
                {{movie.title}}
                {{movie.original_language}}
                {{movie.vote_average}}

                </li>
            </ul>
        </div>

    </div>
</template>

<script>
export default{
    props:{
        moviesList:Array
    },
}

</script>

<style lang="scss" scoped>

</style>