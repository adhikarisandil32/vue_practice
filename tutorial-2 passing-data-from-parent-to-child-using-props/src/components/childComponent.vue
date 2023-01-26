<template>
    <h1>{{msg}}</h1>
    <h2>{{user}}</h2>
    <button v-on:click="getData">Click</button>
</template>

<script>


    export default {
        data(){
            return {
                
            }
        },
        methods:{
            
        },
        //in this section, we define the datatype of props with with the dataType capitalized
        props:{
            msg: String,
            user: Object,
            getData: Function
        }
    }
</script>

<style>

</style>