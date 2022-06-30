<template>
    <div>

        {{ vote5 }}
        <i class="fa-solid fa-star"></i>
        <i class="fa-regular fa-star"></i>
    </div>

</template>

<script>
export default {
    props: {
        vote: Number

    },
    computed: {
        vote5() {
            return Math.ceil(this.vote / 2);
        },

    },
}

</script>

<style lang="scss" scoped>
</style>