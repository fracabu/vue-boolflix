<template>
    <div>
        <input type="text" v-model="userInput">
        <button @click = "startSearch">cerca</button>
    </div>
</template>

<script >
export default{
    data(){
        return{
            userInput:"",
        };
    },
    methods :{
        startSearch(){

            this.$emit("searchTextChanged" , this.userInput)

        }
    }
}

</script>

<style lang="scss" scoped>

</style>