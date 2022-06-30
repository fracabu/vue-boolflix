<template>
    <div>
        <img :src="posterImage " alt="">

    </div>
</template>

<script>

    export default{
        props:{
            movie:Object,
        },
        computed:{
            posterImage(){
                const urlBase = "https://image.tmdb.org/t/p/";
                const imgSize = "w342";
                return urlBase + imgSize + this.movie.poster_path;
            }
        }
        
    }

</script>

<style lang="scss" scoped>

</style>