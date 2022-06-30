<template>
    <div>
        {{vote5}}
    </div>
</template>
<i class="fa-solid fa-star"></i>
<script>
export default {
    props:{
        vote: Number

    }, 
    computed:{
        vote5(){
        return Math.ceil(this.vote / 2);
        },

    },
}

</script>

<style lang="scss" scoped>

</style>