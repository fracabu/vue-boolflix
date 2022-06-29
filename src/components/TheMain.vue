<template>
    <div>
        <div class="moviesList">
            <ul>
                <li v-for = "movie in moviesList" :key="movie.id">
                {{movie.original_title}}
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